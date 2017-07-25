## Scenario 2: Sound&Light and relay

#### What problem does Scenario 2 solve?

short description the scenario 2.  
And how we do.

#### Hardware setup

which Grove will be use and how to connect.

#### Azure services

* Micrsoft Azure IoT Hub: Use to manage and monitor Grove module.
* Micrsoft Azure Functions: We can use fuction to measures temperature and humidity data, and send an alert email via third-party email service.
* IFTTT Maker Channel: It's a webhook services, you need to sign up account and generate an unique URL by yourself.

#### Up and run

**set up**



**code**

```csharp
using Microsoft.Azure.Devices;
using Newtonsoft.Json;
using RestSharp;
using System;

// Get ifttt maker profile, refer to: https://ifttt.com/services/maker_webhooks/settings
// Copy URL of Account Info to browser, then set the event name.
const String maker_service_key = "YOUR-MAKER-SERVICE-KEY";
const string trigger_event_name = "YOUR-MARKER-EVENT-NAME";

const string IOTHUB_CONNECT_STRING = "YOUR_IOTHUB_CONNECT_STRING";

const int BIG_SOUND = 150;

public static void Run(string myEventHubMessage, TraceWriter log)
{
    log.Info($"C# Event Hub trigger function processed a message: {myEventHubMessage}");
    GroveMessage m = JsonConvert.DeserializeObject<GroveMessage>(myEventHubMessage);
    if (m.Sound > BIG_SOUND)
    {
        TriggerIFTTTMaker(m.Sound);
        ControlRelayAsync(m.DeviceId, true).Wait();
    } else
    {
        ControlRelayAsync(m.DeviceId, false).Wait();
    }
}

public static void TriggerIFTTTMaker(int sound)
{
    var client = new RestClient(string.Format("https://maker.ifttt.com/trigger/{0}/with/key/{1}", trigger_event_name, maker_service_key));
    var request = new RestRequest(Method.POST);
    request.AddHeader("cache-control", "no-cache");
    request.AddHeader("content-type", "application/json");
    var body = new
    {
        value1 = sound,
        value2 = "",
        value3 = ""
    };
    request.AddParameter("application/json", JsonConvert.SerializeObject(body), ParameterType.RequestBody);
    IRestResponse response = client.Execute(request);
}

public static async Task ControlRelayAsync(String deviceId, bool onOff)
{
    var methodInvocation = new CloudToDeviceMethod("ControlRelay") { ResponseTimeout = TimeSpan.FromSeconds(30) };
    var message = new { onoff = onOff };
    string messageString = JsonConvert.SerializeObject(message);
    methodInvocation.SetPayloadJson(messageString);
    ServiceClient serviceClient = ServiceClient.CreateFromConnectionString(IOTHUB_CONNECT_STRING);
    var response = await serviceClient.InvokeDeviceMethodAsync(deviceId, methodInvocation);
}

private class GroveMessage
{
    public string DeviceId { get; set; }
    public double Hum { get; set; }
    public double Temp { get; set; }
    public int Sound { get; set; }
    public int Light { get; set; }
    public int GasSO { get; set; }
    public bool PIR { get; set; }
    public string Timestamp { get; set; }
}
```

#### Outcome

The result after running program.

