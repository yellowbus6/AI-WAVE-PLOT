import pandas as pd
import matplotlib.pyplot as plt

stock_symbols = ["AAPL", "AI", "AMD", "AMZN", "AVGO", "CSCO", "GOOGL", "IBM", "MSFT", "NVDA", "PANW", "PATH", "QCOM", "SNOW", "TSM", "TXN"]
stock_data = {}
for symbol in stock_symbols:
    file_name = f"{symbol}.csv"
    stock_data[symbol] = pd.read_csv(file_name)

plt.figure(figsize=(12, 6))
plt.title("AI WAVE")

for symbol, data in stock_data.items():
    plt.plot(data['Date'], data['Close'], label = symbol)
    plt.xlabel("Date")
    plt.ylabel("Price")
    plt.legend()
    plt.grid(True)


plt.show()
