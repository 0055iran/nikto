import requests

def get_dogecoin_price():
    url = 'https://api.coingecko.com/api/v3/simple/price'
    params = {
        'ids': 'dogecoin',
        'vs_currencies': 'usd'
    }
    response = requests.get(url, params=params)
    data = response.json()
    return data['dogecoin']['usd']

price = get_dogecoin_price()
print(f"The current price of Dogecoin is ${price} USD.")