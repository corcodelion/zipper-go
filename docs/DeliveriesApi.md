# DeliveriesApi

All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**cancelDelivery**](DeliveriesApi.md#cancelDelivery) | **POST** /api/v1/deliveries/{deliveryId}/cancel | Cancel a delivery |
| [**cancelDeliveryWithHttpInfo**](DeliveriesApi.md#cancelDeliveryWithHttpInfo) | **POST** /api/v1/deliveries/{deliveryId}/cancel | Cancel a delivery |
| [**createDelivery**](DeliveriesApi.md#createDelivery) | **POST** /api/v1/deliveries | Create a delivery |
| [**createDeliveryWithHttpInfo**](DeliveriesApi.md#createDeliveryWithHttpInfo) | **POST** /api/v1/deliveries | Create a delivery |
| [**getDelivery**](DeliveriesApi.md#getDelivery) | **GET** /api/v1/deliveries/{deliveryId} | Get delivery status |
| [**getDeliveryWithHttpInfo**](DeliveriesApi.md#getDeliveryWithHttpInfo) | **GET** /api/v1/deliveries/{deliveryId} | Get delivery status |
| [**getDeliveryLabel**](DeliveriesApi.md#getDeliveryLabel) | **GET** /api/v1/deliveries/{hubTrackingNumber}/label | Get delivery label metadata |
| [**getDeliveryLabelWithHttpInfo**](DeliveriesApi.md#getDeliveryLabelWithHttpInfo) | **GET** /api/v1/deliveries/{hubTrackingNumber}/label | Get delivery label metadata |
| [**getDeliveryLabelAsset**](DeliveriesApi.md#getDeliveryLabelAsset) | **GET** /api/v1/deliveries/{hubTrackingNumber}/label/{filename} | Download a label asset |
| [**getDeliveryLabelAssetWithHttpInfo**](DeliveriesApi.md#getDeliveryLabelAssetWithHttpInfo) | **GET** /api/v1/deliveries/{hubTrackingNumber}/label/{filename} | Download a label asset |
| [**getHandshakeDelivery**](DeliveriesApi.md#getHandshakeDelivery) | **GET** /api/v1/deliveries/{deliveryId}/handshake | Get handshake PIN info |
| [**getHandshakeDeliveryWithHttpInfo**](DeliveriesApi.md#getHandshakeDeliveryWithHttpInfo) | **GET** /api/v1/deliveries/{deliveryId}/handshake | Get handshake PIN info |
| [**getQuote**](DeliveriesApi.md#getQuote) | **POST** /api/v1/deliveries/quote | Get a delivery quote |
| [**getQuoteWithHttpInfo**](DeliveriesApi.md#getQuoteWithHttpInfo) | **POST** /api/v1/deliveries/quote | Get a delivery quote |
| [**searchDeliveries**](DeliveriesApi.md#searchDeliveries) | **POST** /api/v1/deliveries/search | Search deliveries |
| [**searchDeliveriesWithHttpInfo**](DeliveriesApi.md#searchDeliveriesWithHttpInfo) | **POST** /api/v1/deliveries/search | Search deliveries |
| [**trackDelivery**](DeliveriesApi.md#trackDelivery) | **GET** /api/v1/deliveries/track/{hubTrackingNumber} | Track delivery by tracking number |
| [**trackDeliveryWithHttpInfo**](DeliveriesApi.md#trackDeliveryWithHttpInfo) | **GET** /api/v1/deliveries/track/{hubTrackingNumber} | Track delivery by tracking number |



## cancelDelivery

> HubCancelDeliveryResponse cancelDelivery(deliveryId)

Cancel a delivery

Cancels a delivery that is in CREATED or ASSIGNED status. If the delivery has been dispatched to a provider, the cancellation is also forwarded to the provider.

### Example

```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("http://localhost");
        
        // Configure HTTP bearer authorization: bearerAuth
        HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
        bearerAuth.setBearerToken("BEARER TOKEN");

        DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
        UUID deliveryId = UUID.fromString("550e8400-e29b-41d4-a716-446655440000"); // UUID | UUID of the delivery to cancel
        try {
            HubCancelDeliveryResponse result = apiInstance.cancelDelivery(deliveryId);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling DeliveriesApi#cancelDelivery");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **deliveryId** | **UUID**| UUID of the delivery to cancel | |

### Return type

[**HubCancelDeliveryResponse**](HubCancelDeliveryResponse.md)


### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Delivery cancelled successfully |  -  |
| **404** | Delivery not found |  -  |
| **409** | Delivery cannot be cancelled in its current status |  -  |
| **422** | Provider cancellation failed |  -  |

## cancelDeliveryWithHttpInfo

> ApiResponse<HubCancelDeliveryResponse> cancelDelivery cancelDeliveryWithHttpInfo(deliveryId)

Cancel a delivery

Cancels a delivery that is in CREATED or ASSIGNED status. If the delivery has been dispatched to a provider, the cancellation is also forwarded to the provider.

### Example

```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.ApiResponse;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("http://localhost");
        
        // Configure HTTP bearer authorization: bearerAuth
        HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
        bearerAuth.setBearerToken("BEARER TOKEN");

        DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
        UUID deliveryId = UUID.fromString("550e8400-e29b-41d4-a716-446655440000"); // UUID | UUID of the delivery to cancel
        try {
            ApiResponse<HubCancelDeliveryResponse> response = apiInstance.cancelDeliveryWithHttpInfo(deliveryId);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling DeliveriesApi#cancelDelivery");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **deliveryId** | **UUID**| UUID of the delivery to cancel | |

### Return type

ApiResponse<[**HubCancelDeliveryResponse**](HubCancelDeliveryResponse.md)>


### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Delivery cancelled successfully |  -  |
| **404** | Delivery not found |  -  |
| **409** | Delivery cannot be cancelled in its current status |  -  |
| **422** | Provider cancellation failed |  -  |


## createDelivery

> HubCreateDeliveryResponse createDelivery(hubCreateDeliveryRequest, idempotencyKey)

Create a delivery

Dispatches a new delivery order to the best available carrier provider. An optional idempotency key prevents duplicate orders.

### Example

```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("http://localhost");
        
        // Configure HTTP bearer authorization: bearerAuth
        HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
        bearerAuth.setBearerToken("BEARER TOKEN");

        DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
        HubCreateDeliveryRequest hubCreateDeliveryRequest = new HubCreateDeliveryRequest(); // HubCreateDeliveryRequest | 
        String idempotencyKey = "idempotencyKey_example"; // String | Unique key to ensure idempotent delivery creation
        try {
            HubCreateDeliveryResponse result = apiInstance.createDelivery(hubCreateDeliveryRequest, idempotencyKey);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling DeliveriesApi#createDelivery");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **hubCreateDeliveryRequest** | [**HubCreateDeliveryRequest**](HubCreateDeliveryRequest.md)|  | |
| **idempotencyKey** | **String**| Unique key to ensure idempotent delivery creation | [optional] |

### Return type

[**HubCreateDeliveryResponse**](HubCreateDeliveryResponse.md)


### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Delivery created successfully |  -  |
| **400** | Invalid request parameters |  -  |
| **403** | Forbidden — insufficient permissions |  -  |
| **409** | Duplicate idempotency key |  -  |
| **500** | Internal server error |  -  |

## createDeliveryWithHttpInfo

> ApiResponse<HubCreateDeliveryResponse> createDelivery createDeliveryWithHttpInfo(hubCreateDeliveryRequest, idempotencyKey)

Create a delivery

Dispatches a new delivery order to the best available carrier provider. An optional idempotency key prevents duplicate orders.

### Example

```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.ApiResponse;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("http://localhost");
        
        // Configure HTTP bearer authorization: bearerAuth
        HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
        bearerAuth.setBearerToken("BEARER TOKEN");

        DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
        HubCreateDeliveryRequest hubCreateDeliveryRequest = new HubCreateDeliveryRequest(); // HubCreateDeliveryRequest | 
        String idempotencyKey = "idempotencyKey_example"; // String | Unique key to ensure idempotent delivery creation
        try {
            ApiResponse<HubCreateDeliveryResponse> response = apiInstance.createDeliveryWithHttpInfo(hubCreateDeliveryRequest, idempotencyKey);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling DeliveriesApi#createDelivery");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **hubCreateDeliveryRequest** | [**HubCreateDeliveryRequest**](HubCreateDeliveryRequest.md)|  | |
| **idempotencyKey** | **String**| Unique key to ensure idempotent delivery creation | [optional] |

### Return type

ApiResponse<[**HubCreateDeliveryResponse**](HubCreateDeliveryResponse.md)>


### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Delivery created successfully |  -  |
| **400** | Invalid request parameters |  -  |
| **403** | Forbidden — insufficient permissions |  -  |
| **409** | Duplicate idempotency key |  -  |
| **500** | Internal server error |  -  |


## getDelivery

> HubDeliveryStatusResponse getDelivery(deliveryId)

Get delivery status

Retrieves the current status, tracking information, and full status history of a delivery.

### Example

```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("http://localhost");
        
        // Configure HTTP bearer authorization: bearerAuth
        HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
        bearerAuth.setBearerToken("BEARER TOKEN");

        DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
        UUID deliveryId = UUID.fromString("550e8400-e29b-41d4-a716-446655440000"); // UUID | UUID of the delivery to retrieve
        try {
            HubDeliveryStatusResponse result = apiInstance.getDelivery(deliveryId);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling DeliveriesApi#getDelivery");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **deliveryId** | **UUID**| UUID of the delivery to retrieve | |

### Return type

[**HubDeliveryStatusResponse**](HubDeliveryStatusResponse.md)


### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Delivery details returned |  -  |
| **403** | Forbidden — insufficient permissions |  -  |
| **404** | Delivery not found |  -  |
| **500** | Internal server error |  -  |

## getDeliveryWithHttpInfo

> ApiResponse<HubDeliveryStatusResponse> getDelivery getDeliveryWithHttpInfo(deliveryId)

Get delivery status

Retrieves the current status, tracking information, and full status history of a delivery.

### Example

```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.ApiResponse;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("http://localhost");
        
        // Configure HTTP bearer authorization: bearerAuth
        HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
        bearerAuth.setBearerToken("BEARER TOKEN");

        DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
        UUID deliveryId = UUID.fromString("550e8400-e29b-41d4-a716-446655440000"); // UUID | UUID of the delivery to retrieve
        try {
            ApiResponse<HubDeliveryStatusResponse> response = apiInstance.getDeliveryWithHttpInfo(deliveryId);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling DeliveriesApi#getDelivery");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **deliveryId** | **UUID**| UUID of the delivery to retrieve | |

### Return type

ApiResponse<[**HubDeliveryStatusResponse**](HubDeliveryStatusResponse.md)>


### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Delivery details returned |  -  |
| **403** | Forbidden — insufficient permissions |  -  |
| **404** | Delivery not found |  -  |
| **500** | Internal server error |  -  |


## getDeliveryLabel

> HubDeliveryLabelResponse getDeliveryLabel(hubTrackingNumber)

Get delivery label metadata

Returns barcode value and URLs for barcode image, QR code, and label PDF for a delivery identified by its hub tracking number.

### Example

```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("http://localhost");
        
        // Configure HTTP bearer authorization: bearerAuth
        HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
        bearerAuth.setBearerToken("BEARER TOKEN");

        DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
        String hubTrackingNumber = "HUB-0000001000"; // String | Hub tracking number
        try {
            HubDeliveryLabelResponse result = apiInstance.getDeliveryLabel(hubTrackingNumber);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling DeliveriesApi#getDeliveryLabel");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **hubTrackingNumber** | **String**| Hub tracking number | |

### Return type

[**HubDeliveryLabelResponse**](HubDeliveryLabelResponse.md)


### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Label metadata returned |  -  |
| **404** | Delivery not found |  -  |

## getDeliveryLabelWithHttpInfo

> ApiResponse<HubDeliveryLabelResponse> getDeliveryLabel getDeliveryLabelWithHttpInfo(hubTrackingNumber)

Get delivery label metadata

Returns barcode value and URLs for barcode image, QR code, and label PDF for a delivery identified by its hub tracking number.

### Example

```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.ApiResponse;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("http://localhost");
        
        // Configure HTTP bearer authorization: bearerAuth
        HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
        bearerAuth.setBearerToken("BEARER TOKEN");

        DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
        String hubTrackingNumber = "HUB-0000001000"; // String | Hub tracking number
        try {
            ApiResponse<HubDeliveryLabelResponse> response = apiInstance.getDeliveryLabelWithHttpInfo(hubTrackingNumber);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling DeliveriesApi#getDeliveryLabel");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **hubTrackingNumber** | **String**| Hub tracking number | |

### Return type

ApiResponse<[**HubDeliveryLabelResponse**](HubDeliveryLabelResponse.md)>


### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Label metadata returned |  -  |
| **404** | Delivery not found |  -  |


## getDeliveryLabelAsset

> File getDeliveryLabelAsset(hubTrackingNumber, filename)

Download a label asset

Serves a label asset (barcode.png, qrcode.png, or label.pdf) for a delivery. Streams from storage or generates on-the-fly if not yet uploaded.

### Example

```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("http://localhost");
        
        // Configure HTTP bearer authorization: bearerAuth
        HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
        bearerAuth.setBearerToken("BEARER TOKEN");

        DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
        String hubTrackingNumber = "HUB-0000001000"; // String | Hub tracking number
        String filename = "barcode.png"; // String | Asset filename
        try {
            File result = apiInstance.getDeliveryLabelAsset(hubTrackingNumber, filename);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling DeliveriesApi#getDeliveryLabelAsset");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **hubTrackingNumber** | **String**| Hub tracking number | |
| **filename** | **String**| Asset filename | |

### Return type

[**File**](File.md)


### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Asset returned |  -  |
| **400** | Invalid filename |  -  |
| **404** | Delivery not found |  -  |

## getDeliveryLabelAssetWithHttpInfo

> ApiResponse<File> getDeliveryLabelAsset getDeliveryLabelAssetWithHttpInfo(hubTrackingNumber, filename)

Download a label asset

Serves a label asset (barcode.png, qrcode.png, or label.pdf) for a delivery. Streams from storage or generates on-the-fly if not yet uploaded.

### Example

```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.ApiResponse;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("http://localhost");
        
        // Configure HTTP bearer authorization: bearerAuth
        HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
        bearerAuth.setBearerToken("BEARER TOKEN");

        DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
        String hubTrackingNumber = "HUB-0000001000"; // String | Hub tracking number
        String filename = "barcode.png"; // String | Asset filename
        try {
            ApiResponse<File> response = apiInstance.getDeliveryLabelAssetWithHttpInfo(hubTrackingNumber, filename);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling DeliveriesApi#getDeliveryLabelAsset");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **hubTrackingNumber** | **String**| Hub tracking number | |
| **filename** | **String**| Asset filename | |

### Return type

ApiResponse<[**File**](File.md)>


### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Asset returned |  -  |
| **400** | Invalid filename |  -  |
| **404** | Delivery not found |  -  |


## getHandshakeDelivery

> HubHandshakeDeliveryResponse getHandshakeDelivery(deliveryId)

Get handshake PIN info

Returns PIN handshake information for a delivery, including whether a PIN is required and the PIN code if applicable.

### Example

```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("http://localhost");
        
        // Configure HTTP bearer authorization: bearerAuth
        HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
        bearerAuth.setBearerToken("BEARER TOKEN");

        DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
        UUID deliveryId = UUID.fromString("550e8400-e29b-41d4-a716-446655440000"); // UUID | UUID of the delivery
        try {
            HubHandshakeDeliveryResponse result = apiInstance.getHandshakeDelivery(deliveryId);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling DeliveriesApi#getHandshakeDelivery");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **deliveryId** | **UUID**| UUID of the delivery | |

### Return type

[**HubHandshakeDeliveryResponse**](HubHandshakeDeliveryResponse.md)


### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Handshake info returned |  -  |
| **403** | Forbidden — insufficient permissions |  -  |
| **404** | Delivery not found |  -  |

## getHandshakeDeliveryWithHttpInfo

> ApiResponse<HubHandshakeDeliveryResponse> getHandshakeDelivery getHandshakeDeliveryWithHttpInfo(deliveryId)

Get handshake PIN info

Returns PIN handshake information for a delivery, including whether a PIN is required and the PIN code if applicable.

### Example

```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.ApiResponse;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("http://localhost");
        
        // Configure HTTP bearer authorization: bearerAuth
        HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
        bearerAuth.setBearerToken("BEARER TOKEN");

        DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
        UUID deliveryId = UUID.fromString("550e8400-e29b-41d4-a716-446655440000"); // UUID | UUID of the delivery
        try {
            ApiResponse<HubHandshakeDeliveryResponse> response = apiInstance.getHandshakeDeliveryWithHttpInfo(deliveryId);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling DeliveriesApi#getHandshakeDelivery");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **deliveryId** | **UUID**| UUID of the delivery | |

### Return type

ApiResponse<[**HubHandshakeDeliveryResponse**](HubHandshakeDeliveryResponse.md)>


### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Handshake info returned |  -  |
| **403** | Forbidden — insufficient permissions |  -  |
| **404** | Delivery not found |  -  |


## getQuote

> HubDeliveryQuoteResponse getQuote(hubDeliveryQuoteRequest)

Get a delivery quote

Returns a price quote and estimated arrival time for the given pickup/dropoff route and delivery type.

### Example

```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("http://localhost");
        
        // Configure HTTP bearer authorization: bearerAuth
        HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
        bearerAuth.setBearerToken("BEARER TOKEN");

        DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
        HubDeliveryQuoteRequest hubDeliveryQuoteRequest = new HubDeliveryQuoteRequest(); // HubDeliveryQuoteRequest | 
        try {
            HubDeliveryQuoteResponse result = apiInstance.getQuote(hubDeliveryQuoteRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling DeliveriesApi#getQuote");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **hubDeliveryQuoteRequest** | [**HubDeliveryQuoteRequest**](HubDeliveryQuoteRequest.md)|  | |

### Return type

[**HubDeliveryQuoteResponse**](HubDeliveryQuoteResponse.md)


### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Quote returned successfully |  -  |
| **400** | Invalid request parameters |  -  |
| **403** | Forbidden — insufficient permissions |  -  |
| **500** | Internal server error |  -  |

## getQuoteWithHttpInfo

> ApiResponse<HubDeliveryQuoteResponse> getQuote getQuoteWithHttpInfo(hubDeliveryQuoteRequest)

Get a delivery quote

Returns a price quote and estimated arrival time for the given pickup/dropoff route and delivery type.

### Example

```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.ApiResponse;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("http://localhost");
        
        // Configure HTTP bearer authorization: bearerAuth
        HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
        bearerAuth.setBearerToken("BEARER TOKEN");

        DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
        HubDeliveryQuoteRequest hubDeliveryQuoteRequest = new HubDeliveryQuoteRequest(); // HubDeliveryQuoteRequest | 
        try {
            ApiResponse<HubDeliveryQuoteResponse> response = apiInstance.getQuoteWithHttpInfo(hubDeliveryQuoteRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling DeliveriesApi#getQuote");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **hubDeliveryQuoteRequest** | [**HubDeliveryQuoteRequest**](HubDeliveryQuoteRequest.md)|  | |

### Return type

ApiResponse<[**HubDeliveryQuoteResponse**](HubDeliveryQuoteResponse.md)>


### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Quote returned successfully |  -  |
| **400** | Invalid request parameters |  -  |
| **403** | Forbidden — insufficient permissions |  -  |
| **500** | Internal server error |  -  |


## searchDeliveries

> PageResponseListHubDeliverySearchDTO searchDeliveries(searchDeliveriesRequest)

Search deliveries

Search and filter deliveries with pagination. Supports filtering by status, date range, and other criteria. Returns a paginated list of deliveries matching the search parameters.

### Example

```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("http://localhost");
        
        // Configure HTTP bearer authorization: bearerAuth
        HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
        bearerAuth.setBearerToken("BEARER TOKEN");

        DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
        SearchDeliveriesRequest searchDeliveriesRequest = new SearchDeliveriesRequest(); // SearchDeliveriesRequest | 
        try {
            PageResponseListHubDeliverySearchDTO result = apiInstance.searchDeliveries(searchDeliveriesRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling DeliveriesApi#searchDeliveries");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **searchDeliveriesRequest** | [**SearchDeliveriesRequest**](SearchDeliveriesRequest.md)|  | |

### Return type

[**PageResponseListHubDeliverySearchDTO**](PageResponseListHubDeliverySearchDTO.md)


### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Search results returned |  -  |
| **403** | Forbidden |  -  |

## searchDeliveriesWithHttpInfo

> ApiResponse<PageResponseListHubDeliverySearchDTO> searchDeliveries searchDeliveriesWithHttpInfo(searchDeliveriesRequest)

Search deliveries

Search and filter deliveries with pagination. Supports filtering by status, date range, and other criteria. Returns a paginated list of deliveries matching the search parameters.

### Example

```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.ApiResponse;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("http://localhost");
        
        // Configure HTTP bearer authorization: bearerAuth
        HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
        bearerAuth.setBearerToken("BEARER TOKEN");

        DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
        SearchDeliveriesRequest searchDeliveriesRequest = new SearchDeliveriesRequest(); // SearchDeliveriesRequest | 
        try {
            ApiResponse<PageResponseListHubDeliverySearchDTO> response = apiInstance.searchDeliveriesWithHttpInfo(searchDeliveriesRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling DeliveriesApi#searchDeliveries");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **searchDeliveriesRequest** | [**SearchDeliveriesRequest**](SearchDeliveriesRequest.md)|  | |

### Return type

ApiResponse<[**PageResponseListHubDeliverySearchDTO**](PageResponseListHubDeliverySearchDTO.md)>


### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Search results returned |  -  |
| **403** | Forbidden |  -  |


## trackDelivery

> HubDeliveryStatusResponse trackDelivery(hubTrackingNumber)

Track delivery by tracking number

Retrieves delivery status and tracking information using the hub tracking number. This endpoint is designed for easy tracking URL sharing and does not require authentication, but will only return information for deliveries that have been marked as &#39;trackable&#39; by the sender.

### Example

```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("http://localhost");
        
        // Configure HTTP bearer authorization: bearerAuth
        HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
        bearerAuth.setBearerToken("BEARER TOKEN");

        DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
        String hubTrackingNumber = "HUB-0000001000"; // String | Hub tracking number
        try {
            HubDeliveryStatusResponse result = apiInstance.trackDelivery(hubTrackingNumber);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling DeliveriesApi#trackDelivery");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **hubTrackingNumber** | **String**| Hub tracking number | |

### Return type

[**HubDeliveryStatusResponse**](HubDeliveryStatusResponse.md)


### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Delivery details returned |  -  |
| **404** | Delivery not found |  -  |

## trackDeliveryWithHttpInfo

> ApiResponse<HubDeliveryStatusResponse> trackDelivery trackDeliveryWithHttpInfo(hubTrackingNumber)

Track delivery by tracking number

Retrieves delivery status and tracking information using the hub tracking number. This endpoint is designed for easy tracking URL sharing and does not require authentication, but will only return information for deliveries that have been marked as &#39;trackable&#39; by the sender.

### Example

```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.ApiResponse;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.DeliveriesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("http://localhost");
        
        // Configure HTTP bearer authorization: bearerAuth
        HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
        bearerAuth.setBearerToken("BEARER TOKEN");

        DeliveriesApi apiInstance = new DeliveriesApi(defaultClient);
        String hubTrackingNumber = "HUB-0000001000"; // String | Hub tracking number
        try {
            ApiResponse<HubDeliveryStatusResponse> response = apiInstance.trackDeliveryWithHttpInfo(hubTrackingNumber);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling DeliveriesApi#trackDelivery");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **hubTrackingNumber** | **String**| Hub tracking number | |

### Return type

ApiResponse<[**HubDeliveryStatusResponse**](HubDeliveryStatusResponse.md)>


### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Delivery details returned |  -  |
| **404** | Delivery not found |  -  |

