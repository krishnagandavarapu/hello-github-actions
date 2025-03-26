def coinChange(coins, amount):
    coins.sort(reverse=True)  # Sort coins in descending order
    count = 0
    
    for coin in coins:
        if amount == 0:
            break
        count += amount // coin  # Take maximum possible coins of this denomination
        amount %= coin  # Update remaining amount

    return count if amount == 0 else -1  # If amount is 0, return count; otherwise, return -1

coins = [1, 2, 5]
amount = 11
print(coinChange(coins, amount))  
