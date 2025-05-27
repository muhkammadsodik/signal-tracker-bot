from telegram import Update
from telegram.ext import ApplicationBuilder, CommandHandler, ContextTypes

async def start(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text("Salom! Crypto Arbitrage botiga xush kelibsiz!")

async def help_command(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text("Yordam: /start yoki /help dan foydalaning.")

app = ApplicationBuilder().token('BU_YERGA_TOKEN_YOZING').build()
app.add_handler(CommandHandler("start", start))
app.add_handler(CommandHandler("help", help_command))

print("✅ Bot ishga tushdi.")
app.run_polling()