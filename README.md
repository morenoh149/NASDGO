# NASDGO

Golang implementaion of a stock exchange

## Requirements
1. unlikelly to lose customer orders
1. Clients interface via HTTP
1. limit orders

## Architecture
* start with https://github.com/gobuffalo/buffalo
* account management
* matching engine (exchange engine, order book)
  * real-time
* order management
* treasure to hold funds
* keep as much in memory as possible
  * use redis
* use two threads
  * order matching thread
  * persistence thread writing to rabbitmq
* pin thread to cpu
  * [cpuset](http://man7.org/linux/man-pages/man7/cpuset.7.html)
* order persistence with rabbitmq

## User Stories
1. if Mark is trying to sell 250 IBM at $10 a share, and you have John trying to buy 100 IBM at $11 a share, and Clara trying to buy 300 IBM at $9 a share, John is the one who is going to get filled at $10 a share (or maybe it would fill at $11 to Mark’s advantage)

## Wishlist
* FIX
* FAST
* ITCH
* websocket for order data to clients

## links 
* http://www.nyxdata.com/capacity
