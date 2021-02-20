# BetterAntiSpam 2.0
This bot is a clone of BetterAntiSpam with the same commands! I would recomment cloning using <button><a href= "https://repl.it/~">repl.it</a></button>

# Getting Started
If you are coding in <button><a href= "https://repl.it/~">repl.it</a> </button> first go to **.replit** make sure it is npm start

# How to Start My bot?
Make a new file called **.env** and write this `token=YOUR_BOT_TOKEN_HERE` after you've done you can choose your bot prefix in **server.js** at `prefix: "YOUR_BOT_PREFIX"`

# How to add Command handler?
Go to **server.js** and paste this down
`const dbd = require("dbd.js")
 
const bot = new dbd.Bot({
token: process.env.token, 
prefix: "!" //change this if you want another prefix! 
})
 
bot.onMessage()
 
const fs = require('fs')

const folders = fs.readdirSync("./commands/")

for (const files of folders) {
const folder = fs.readdirSync(`./commands/${files}/`).filter(file => file.endsWith(".js"))

for (const commands of folder) {
const command = require(`./commands/${files}/${commands}`) 
bot.command(command)
} 
}`
