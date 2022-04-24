# BoogieFN-Bot
The Discord Bot Used For BoogieFN

Python Backend Example
.. code:: py
@app.route("/change/vbucs/<id>/<amount>")
async def crown(request, id, amount):
  dirr = f'files/config/profiles/{id}/settings.json'
  with open(dirr) as f:
    data = json.load(f)
  data['v-bucks'] = int(amount)
  with open (dirr,'w+') as f:
    json.dump(data, f, indent=3)
  return sanic.response.json({})
  
