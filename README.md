# youtube-url-2-playlist-id
```js
(async () => {
    const urls = ['https://www.youtube.com/c/ivarlamov','https://www.youtube.com/c/UtopiaShow']
    const result = []    
    for (const u of urls) {
        try {
            const htmlRaw = await fetch(u,{method:"GET"}).then(e=>e.text())
            const playlistId = /"channelUrl":"(.*)","isFamilySafe"/.exec(htmlRaw)[1]
            console.log(result.push(playlistId),u,playlistId)
        } catch(e) {console.error(e.message)}       
    }
    console.log(result)
})()
```
How to use:
![youtube_url-2-playlist-id](https://user-images.githubusercontent.com/39878271/178428119-d9f396db-d653-4048-96ac-648712fdf5bb.png)
