{% method %}
## GET media/{mediaName}
Downloads a media file you previously uploaded.

{% common %}
### Example: Download an MP3 File

{% sample lang="bash" %}
```bash
# Coming soon
```

{% sample lang="js" %}
```js
//Coming soon
```

{% sample lang="csharp" %}
```csharp
using(var data = await client.Media.DownloadAsync("file.mp3"))
{
  var fileContent = await data.ReadAsStreamAsync();
}
```

{% sample lang="ruby" %}
```ruby
content, media_type = Media.download(client, "file.mp3")
```
{% endmethod %}