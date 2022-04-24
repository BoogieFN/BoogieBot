# BoogieFN-Bot
The Discord Bot Used For BoogieFN

Python Backend Example
```py
@app.route("/change/vbucs/<id>/<amount>")
async def crown(request, id, amount):
  dirr = f'files/config/profiles/{id}/settings.json'
  with open(dirr) as f:
    data = json.load(f)
  data['v-bucks'] = int(amount)
  with open (dirr,'w+') as f:
    json.dump(data, f, indent=3)
  return sanic.response.json({})
  ```

Javascript Backend Example
```js
app.post('/api/v1/vbucks/:accountId/:vbucks', (req, res) => {
  const vbucks = req.params.vbucks;
  const accountId = req.params.accountId;
  config = JSON.parse(fs.readFileSync(`files/config/profiles/${accountId}/settings.json`));
  
  config.Vbucks = vbucks
  fs.writeFileSync(`files/config/profiles/${accountId}/settings.json`, JSON.stringify(data, null, 2));
})
