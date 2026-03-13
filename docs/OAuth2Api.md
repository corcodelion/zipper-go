# OAuth2Api

All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**token**](OAuth2Api.md#token) | **POST** /api/auth/oauth/token | Exchange client credentials for an access token |
| [**tokenWithHttpInfo**](OAuth2Api.md#tokenWithHttpInfo) | **POST** /api/auth/oauth/token | Exchange client credentials for an access token |



## token

> OAuth2TokenResponse token(grantType, clientId, clientSecret)

Exchange client credentials for an access token

Issues a JWT access token in exchange for valid API client credentials using the client_credentials grant type.

### Example

```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.OAuth2Api;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("http://localhost");
        
        // Configure HTTP bearer authorization: bearerAuth
        HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
        bearerAuth.setBearerToken("BEARER TOKEN");

        OAuth2Api apiInstance = new OAuth2Api(defaultClient);
        String grantType = "grantType_example"; // String | OAuth2 grant type (must be 'client_credentials')
        String clientId = "clientId_example"; // String | API client identifier
        String clientSecret = "clientSecret_example"; // String | API client secret key
        try {
            OAuth2TokenResponse result = apiInstance.token(grantType, clientId, clientSecret);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling OAuth2Api#token");
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
| **grantType** | **String**| OAuth2 grant type (must be &#39;client_credentials&#39;) | |
| **clientId** | **String**| API client identifier | |
| **clientSecret** | **String**| API client secret key | |

### Return type

[**OAuth2TokenResponse**](OAuth2TokenResponse.md)


### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/x-www-form-urlencoded
- **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Access token issued successfully |  -  |
| **400** | Unsupported grant type |  -  |
| **401** | Invalid client credentials or inactive account |  -  |
| **500** | Internal server error |  -  |

## tokenWithHttpInfo

> ApiResponse<OAuth2TokenResponse> token tokenWithHttpInfo(grantType, clientId, clientSecret)

Exchange client credentials for an access token

Issues a JWT access token in exchange for valid API client credentials using the client_credentials grant type.

### Example

```java
// Import classes:
import com.zipper.delivery.hub.sdk.ApiClient;
import com.zipper.delivery.hub.sdk.ApiException;
import com.zipper.delivery.hub.sdk.ApiResponse;
import com.zipper.delivery.hub.sdk.Configuration;
import com.zipper.delivery.hub.sdk.auth.*;
import com.zipper.delivery.hub.sdk.models.*;
import com.zipper.delivery.hub.sdk.api.OAuth2Api;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("http://localhost");
        
        // Configure HTTP bearer authorization: bearerAuth
        HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
        bearerAuth.setBearerToken("BEARER TOKEN");

        OAuth2Api apiInstance = new OAuth2Api(defaultClient);
        String grantType = "grantType_example"; // String | OAuth2 grant type (must be 'client_credentials')
        String clientId = "clientId_example"; // String | API client identifier
        String clientSecret = "clientSecret_example"; // String | API client secret key
        try {
            ApiResponse<OAuth2TokenResponse> response = apiInstance.tokenWithHttpInfo(grantType, clientId, clientSecret);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling OAuth2Api#token");
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
| **grantType** | **String**| OAuth2 grant type (must be &#39;client_credentials&#39;) | |
| **clientId** | **String**| API client identifier | |
| **clientSecret** | **String**| API client secret key | |

### Return type

ApiResponse<[**OAuth2TokenResponse**](OAuth2TokenResponse.md)>


### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/x-www-form-urlencoded
- **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Access token issued successfully |  -  |
| **400** | Unsupported grant type |  -  |
| **401** | Invalid client credentials or inactive account |  -  |
| **500** | Internal server error |  -  |

