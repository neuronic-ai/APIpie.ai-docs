# Upload a file and retrieve URL

## Endpoint: POST /urlshare

[APIpie.ai](https://apipie.ai) provides this endpoint to upload a file to the server and returns a URL where the uploaded file can be accessed temporarily. This endpoint supports uploading images only, images should be 1024x1024, or 1024x768 or 768x1024, otherwise they will be resized automatically. Files larger than 5mb will be rejected.

For more information on file sharing capabilities, visit the [APIpie documentation](https://apipie.ai/docs).

## Request

### Body Parameters

The request should be sent as `multipart/form-data` with the following parameter:

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| file | binary | Yes | File to be uploaded. Supported formats include .png, .jpg, .jpeg, .svg, .gif, .bmp, .tif, .tiff, .webp |

### Example Request

```bash
curl -X POST https://api.apipie.ai/urlshare \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -F "file=@/path/to/your/image.jpg"
```

## Response

### 200 OK

| Property | Type | Description |
|----------|------|-------------|
| url | string | URL to access the uploaded file |

### Example Response

```json
{
  "url": "https://apipie.ai/temp/uniquefilename.jpg"
}
```

### Error Responses

| Status Code | Description |
|-------------|-------------|
| 400 | No file uploaded or the file type is not supported |
| 500 | Internal server error or unable to save file |

## Notes

- Only image files are supported
- Recommended image dimensions: 1024x1024, 1024x768, or 768x1024
- Images with different dimensions will be automatically resized
- Maximum file size: 5MB
- The URL provided is temporary and the file will be automatically deleted after a certain period
- The returned URLs (https://apipie.ai/temp/...) can be used with other [APIpie API endpoints](https://apipie.ai/docs) that require image URLs
