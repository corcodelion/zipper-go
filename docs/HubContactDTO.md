

# HubContactDTO

Contact and location details for a pickup or dropoff point

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**name** | **String** | Contact person name |  |
|**phone** | **String** | Contact phone number |  |
|**email** | **String** | Contact email address |  [optional] |
|**notes** | **String** | Notes or instructions for the driver |  [optional] |
|**location** | [**LocationDTO**](LocationDTO.md) | Geographic location with address details |  |
|**openHours** | [**List&lt;OpenHoursEntryDTO&gt;**](OpenHoursEntryDTO.md) | Pickup availability windows (time-of-day). Null or empty means always available. |  [optional] |
|**timezone** | **String** | IANA timezone of the pickup location, required when openHours is provided |  [optional] |



