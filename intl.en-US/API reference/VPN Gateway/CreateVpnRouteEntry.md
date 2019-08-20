# CreateVpnRouteEntry {#doc_api_Vpc_CreateVpnRouteEntry .reference}

Creates a VPN destination route.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Vpc&api=CreateVpnRouteEntry&type=RPC&version=2016-04-28)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String|Yes|CreateVpnRouteEntry|The name of this action. Value: **CreateVpnRouteEntry**.

 |
|NextHop|String|Yes|vco-bp15oes1py4i66rmd\*\*\*\*|The next hop of the destination route.

 |
|PublishVpc|Boolean|Yes|true|Indicates whether to publish the destination route to the VPC. Valid values:

 -   **true**: The destination route is published to the VPC.
-   **false**: The destination route is not published to the VPC.

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the VPN destination route belongs. To query the region ID, call [DescribeRegions](~~36063~~).

 |
|RouteDest|String|Yes|10.0.0.0/24|The destination CIDR block of the destination route.

 |
|VpnGatewayId|String|Yes|vpn-bp1a3kqjiiq9legfx\*\*\*\*|The ID of the VPN Gateway.

 |
|Weight|Integer|Yes|0|The weight of the destination route. Valid values: **0**|**100**.

 |
|ClientToken|String|No|d7d24a21-f4ba-4454-9173-b3828dae492b|The client token used to guarantee the idempotence of the request.

 The value of this parameter is generated by the client and must be unique among different requests. It must be 1 to 64 ASCII characters in length.

 |
|OverlayMode|String|No|Ipsec|The overwrite mode.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|CreateTime|Long|1492747187000|The time when the VPN destination route was created.

 |
|NextHop|String|vco-bp15oes1py4i66rmd\*\*\*\*|The next hop of the destination route.

 |
|OverlayMode|String|Ipsec|The overwrite mode.

 |
|RequestId|String|5BE01CD7-5A50-472D-AC14-CA181C5C03BE|The ID of the request.

 |
|RouteDest|String|10.0.0.0/24|The destination CIDR block of the destination route.

 |
|State|String|published|The status of the VPN destination route.

 |
|VpnInstanceId|String|vpn-bp1cmw7jh1nfe43m9\*\*\*\*|The ID of the VPN Gateway.

 |
|Weight|Integer|0|The weight of the destination route. Valid value:**0**|**100**.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://[Endpoint]/? Action=CreateVpnRouteEntry
&NextHop=vco-bp15oes1py4i66rmd****	
&PublishVpc=true
&RegionId=cn-hangzhou
&RouteDest=10.0.0.0/24
&VpnGatewayId=vpn-bp1a3kqjiiq9legfx****
&Weight=0
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<CreateVpnRouteEntryResponse>
	  <RouteDest>10.0.0.0/24</RouteDest>
	  <VpnInstanceId>vpn-bp1cmw7jh1nfe43m9****</VpnInstanceId>
	  <OverlayMode>Ipsec</OverlayMode>
	  <State>published</State>
	  <Weight>100</Weight>
	  <CreateTime>1563873294331</CreateTime>
	  <NextHop>vco-bp1tui07ob10fmuro****</NextHop>
      <RequestId>EE4C2417-9437-4333-BDEB-8493F7AA7258</RequestId>
</CreateVpnRouteEntryResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RouteDest":"10.0.0.0/24",
	"VpnInstanceId":"vpn-bp1cmw7jh1nfe43m9****",
	"OverlayMode":"Ipsec",
	"Weight":100,
	"State":"published",
	"RequestId":"CB2793A8-845F-444C-8E93-76F1BBDF9C78",
	"NextHop":"vco-bp1tui07ob10fmuro****",
	"CreateTime":1563873294331
}
```

## Errors { .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|403|Forbidden.SubUser|User not authorized to operate on the specified resource as your account is created by another user.|You are not authorized to use this resource. Apply for the permission and try again.|
|403|Forbidden|User not authorized to operate on the specified resource.|You are not authorized to use this resource. For more information, open a ticket.|
|400|Resource.QuotaFull|The quota of resource is full.|The resource quota has been reached.|
|404|InvalidVpnGatewayInstanceId.NotFound|The specified vpn gateway instance id does not exist.|The specified VPN Gateway does not exist.|
|400|VpnGateway.Configuring|The specified service is configuring.|The specified service is being configured.|
|400|VpnGateway.FinancialLocked|The specified service is financial locked.|The specified service is locked due to insufficient account balance.|
