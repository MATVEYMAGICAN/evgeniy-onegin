import telebot
from telebot import types
import time

bot = telebot.TeleBot("7750911072:AAFpAflixbcDl4Og9bu9irkJo2E3oYOTgg4")
buttons = [
    types.InlineKeyboardButton('История создания', callback_data='history'),
    types.InlineKeyboardButton('Особенности жанра', callback_data='zhanr'),
    types.InlineKeyboardButton('Краткая характеристика персонажей', callback_data='pers'),
    types.InlineKeyboardButton('Подробная характеристика персонажей', callback_data='new_pers'),
    types.InlineKeyboardButton('Читать произведение', callback_data='read'),
    types.InlineKeyboardButton('Тематические особенности', callback_data='theme'),
    types.InlineKeyboardButton('Критика о романе', url='https://www.literaturus.ru/2016/09/kritika-evgenij-onegin-pushkin-otzyvy-sovremennikov.html'),
    types.InlineKeyboardButton('Комментарий Д.Благого', url='https://matveymagican.github.io/blagoy-comment.github.io/'),
    types.InlineKeyboardButton('Сайт с иллюстрациями', url='https://evgenij-onegin.ru/illyustratsii/')
    ]

@bot.callback_query_handler(func=lambda call: call.data == 'theme')
def zhanr(call):
    bot.delete_message(chat_id=call.message.chat.id, message_id=call.message.message_id)
    markup = types.InlineKeyboardMarkup(row_width=1)
    markup.add(*buttons)
    bot.send_message(call.message.chat.id,
                     text="Любовь - Тема любви в романе многогранна: неразделенная любовь Татьяны, страсть Онегина, мимолетная любовь Ленского.\n\nДружба - Дружба Онегина и Ленского, их противоположные характеры и трагические последствия их взаимоотношений.\n\nСмысл жизни - Поиск смысла жизни героями, их разочарования и попытки найти свое место в мире.\n\nОбщество - Описание дворянского общества начала XIX века, его нравы, проблемы и противоречия.\n\nВремя - Роман отражает дух эпохи, ее идеи, ценности и социальные изменения.", reply_markup=markup)


@bot.callback_query_handler(func=lambda call: call.data == 'read')
def zhanr(call):
    bot.delete_message(chat_id=call.message.chat.id, message_id=call.message.message_id)
    markup = types.InlineKeyboardMarkup(row_width=1)
    btn6 = types.InlineKeyboardButton('Аудио', url='https://www.youtube.com/watch?v=DGdPJPvHJA0')
    btn7 = types.InlineKeyboardButton('Текст', url='https://ilibrary.ru/text/436/p.2/index.html')
    markup.add(btn6, btn7, *buttons)
    bot.send_message(call.message.chat.id,
                     text="Выберите формат:", reply_markup=markup)

@bot.callback_query_handler(func=lambda call: call.data == 'zhanr')
def zhanr(call):
    bot.delete_message(chat_id=call.message.chat.id, message_id=call.message.message_id)
    markup = types.InlineKeyboardMarkup(row_width=1)
    btn1 = types.InlineKeyboardButton('Роман', callback_data='roman')
    btn2 = types.InlineKeyboardButton('Стихи', callback_data='stih')
    btn3 = types.InlineKeyboardButton('Реализм', callback_data='realizm')
    btn4 = types.InlineKeyboardButton('Романтизм', callback_data='romantizm')
    btn5 = types.InlineKeyboardButton('Особенности стиля', callback_data='style')
    markup.add(btn1, btn2, btn3, btn4, btn5)
    bot.send_message(call.message.chat.id,
                     text="Выберите пункт:", reply_markup=markup)

@bot.callback_query_handler(func=lambda call: call.data == 'roman')
def bla(call):
    bot.delete_message(chat_id=call.message.chat.id, message_id=call.message.message_id)
    markup = types.InlineKeyboardMarkup(row_width=1)
    markup.add(*buttons)
    bot.send_message(call.message.chat.id,
                     text="«Евгений Онегин» – это роман, который повествует о жизни и переживаниях главного героя.", reply_markup=markup)

@bot.callback_query_handler(func=lambda call: call.data == 'stih')
def bla(call):
    bot.delete_message(chat_id=call.message.chat.id, message_id=call.message.message_id)
    markup = types.InlineKeyboardMarkup(row_width=1)
    markup.add(*buttons)
    bot.send_message(call.message.chat.id,
                     text="Роман написан стихами, что придает ему особую ритмичность и мелодичность.", reply_markup=markup)

@bot.callback_query_handler(func=lambda call: call.data == 'realizm')
def bla(call):
    bot.delete_message(chat_id=call.message.chat.id, message_id=call.message.message_id)
    markup = types.InlineKeyboardMarkup(row_width=1)
    markup.add(*buttons)
    bot.send_message(call.message.chat.id,
                     text="Роман отличается реализмом – он описывает жизнь и быт дворянского общества начала XIX века.", reply_markup=markup)

@bot.callback_query_handler(func=lambda call: call.data == 'romantizm')
def bla(call):
    bot.delete_message(chat_id=call.message.chat.id, message_id=call.message.message_id)
    markup = types.InlineKeyboardMarkup(row_width=1)
    markup.add(*buttons)
    bot.send_message(call.message.chat.id,
                     text="Вместе с тем в романе есть романтические элементы – сильные чувства, драматические события, философские размышления.", reply_markup=markup)

@bot.callback_query_handler(func=lambda call: call.data == 'style')
def bla(call):
    bot.delete_message(chat_id=call.message.chat.id, message_id=call.message.message_id)
    markup = types.InlineKeyboardMarkup(row_width=1)
    markup.add(*buttons)
    bot.send_message(call.message.chat.id,
                     text="Язык - Яркий, образный, богатый, использует народные пословицы и поговорки, создает атмосферу и настроение.\n\nРитм - Четкий, динамичный, создает ощущение движения и жизни, передает чувства героев.\n\nСтрофа - Четырехстопный ямб с женской рифмовкой, создает гармоничную и легко запоминающуюся форму.\n\nЮмор - Ироничный и тонкий, сарказм, насмешка над обществом и персонажами, делает роман более реалистичным.", reply_markup=markup)

@bot.callback_query_handler(func=lambda call: call.data == 'history')
def history(call):
    # Удаление предыдущего сообщения
    bot.delete_message(chat_id=call.message.chat.id, message_id=call.message.message_id)

    # Создаем клавиатуру
    markup = types.InlineKeyboardMarkup(row_width=1)
    markup.add(*buttons)

    # Первое сообщение
    msg1 = bot.send_message(
        call.message.chat.id,
        text="Пушкин задумал роман во время южной ссылки в Кишинёве, где впечатления отразились в первой главе и «Путешествии Онегина». Основную часть он создал в Михайловском, пропитав главы атмосферой деревенской скуки. Черновую версию завершил во время Болдинской осени, сочинив восьмую главу, дописав «Путешествие» и частично уничтожив десятую. Завершил работу в Царском Селе, написав «Письмо Онегина». Роман создавался с мая 1823 по октябрь 1831 года."
    )
    time.sleep(20)
    bot.delete_message(chat_id=call.message.chat.id, message_id=msg1.message_id)  # Удаляем первое сообщение

    # Второе сообщение
    msg2 = bot.send_message(
        call.message.chat.id,
        text="Отрывки публиковались постепенно в журналах, а главы выходили отдельными выпусками. Полное издание появилось в 1833 году. Поэт изменял текст до смерти, исключив из сводных изданий некоторые строфы. Десятая глава с политическим подтекстом (включая упоминание декабристов) была сожжена, но частично восстановлена."
    )
    time.sleep(15)
    bot.delete_message(chat_id=call.message.chat.id, message_id=msg2.message_id)  # Удаляем второе сообщение

    # Третье сообщение
    bot.send_message(
        call.message.chat.id,
        text="Роман встретил противоречивые отзывы современников, включая критику Булгарина и Полевого. Широкое признание пришло спустя десятилетие благодаря Белинскому. Впоследствии «Евгений Онегин» вошёл в школьную программу, в СССР его изучали в идеологически окрашенной трактовке.",
        reply_markup=markup
    )
@bot.callback_query_handler(func=lambda call: call.data == 'pers')
def bla(call):
    bot.delete_message(chat_id=call.message.chat.id, message_id=call.message.message_id)
    markup = types.InlineKeyboardMarkup(row_width=1)
    markup.add(*buttons)
    bot.send_message(call.message.chat.id,
                     text="Онегин - Богатый столичный дворянин, молодой мужчина, которого полюбила Татьяна.\n\nАвтор-рассказчик - Товарищ Онегина, очевидно это Александр Сергеевич Пушкин.\n\nВладимир Ленский - Богатый дворянин, помещик, приятель Онегина, 18 лет.\n\nОльга Ларина - Младшая сестра Татьяны, возлюбленная Ленского.\n\nМать Татьяны и Ольги - Небогатая провинциальная дворянка, пожилая дама.\n\nЗарецкий - Дворянин, сосед и приятель Онегина и Ленского.\n\nКнязь N - Влиятельный столичный аристократ, супруг Татьяны Лариной.\n\nКняжна Алина - Кузина старшей Лариной, то есть двоюродная тётка Татьяны и Ольги.\n\nНяня Татьяны Лариной - Крепостная крестьянка, пожилая женщина.", reply_markup=markup)


@bot.message_handler(commands=['start'])
def start(message):
    markup = types.InlineKeyboardMarkup(row_width=1)
    markup.add(*buttons)
    bot.send_message(message.chat.id,
                     text="Здравствуйте, ценители Пушкинского творчества!\nЯ расскажу вам o произведении А.С.Пушкина 'Евгений Онегин'".format(message.from_user))
    time.sleep(2)
    bot.delete_message(chat_id=message.chat.id, message_id=message.message_id)
    bot.send_message(message.chat.id,
                     text="Выберите что вы бы хотели узнать:", reply_markup=markup)

@bot.callback_query_handler(func=lambda call: call.data == 'new_pers')
def blaaaa(call):
    bot.delete_message(chat_id=call.message.chat.id, message_id=call.message.message_id)
    markup = types.InlineKeyboardMarkup(row_width=1)
    btn1 = types.InlineKeyboardButton('Татьяна Ларина', callback_data='one')
    btn2 = types.InlineKeyboardButton('Автор-рассказчик', callback_data='two')
    btn3 = types.InlineKeyboardButton('Владимир Ленский', callback_data='three')
    btn4 = types.InlineKeyboardButton('Ольга Ларина', callback_data='four')
    btn5 = types.InlineKeyboardButton('Мать Татьяны и Ольги', callback_data='five')
    btn6 = types.InlineKeyboardButton('Зарецкий', callback_data='six')
    btn7 = types.InlineKeyboardButton('Князь N', callback_data='seven')
    btn8 = types.InlineKeyboardButton('Княжна Алина', callback_data='eight')
    btn9 = types.InlineKeyboardButton('Няня Татьяны Лариной', callback_data='nine')
    markup.add(btn1, btn2, btn3, btn4, btn5, btn6, btn7, btn8, btn9)
    bot.send_message(call.message.chat.id,
                     text="Выберите персонажа:", reply_markup=markup)

@bot.callback_query_handler(func=lambda call: call.data == 'one')
def two(call):
    bot.delete_message(chat_id=call.message.chat.id, message_id=call.message.message_id)
    markup = types.InlineKeyboardMarkup(row_width=1)
    markup.add(*buttons)
    bot.send_message(call.message.chat.id,
                     text="Сдержанная, задумчивая, прекрасно воспитанная девушка. Свободное время она с удовольствием проводит с интересной книгой, нежели в шумной компании. Девушка не отличается яркой внешностью, не стремится к обольщению и соблазнению мужчин. Душевное равновесие Татьяны нарушается при встрече с Онегиным, а неразделённые чувства к молодому повесе становятся для нее тяжёлым испытанием. Но, обладая внутренним стержнем, девушка открывает новую главу своей жизни и по настоянию матери выходит замуж за достойного человека.", reply_markup=markup)

@bot.callback_query_handler(func=lambda call: call.data == 'two')
def three(call):
    bot.delete_message(chat_id=call.message.chat.id, message_id=call.message.message_id)
    markup = types.InlineKeyboardMarkup(row_width=1)
    markup.add(*buttons)
    bot.send_message(call.message.chat.id,
                     text="Несмотря на то что в романе не фигурирует имя рассказчика, в ходе повествования становится понятно, что эта роль принадлежит самому Александру Сергеевичу Пушкину. Он часто напоминает о себе, вмешивается в ход событий, в лирических отступлениях делится с читателями своими взглядами на жизнь. Это добрый приятель Онегина, который не скрывает свою искреннюю симпатию к главному герою, ни в чём не упрекает его и прощает ему ошибки.", reply_markup=markup)

@bot.callback_query_handler(func=lambda call: call.data == 'three')
def four(call):
    bot.delete_message(chat_id=call.message.chat.id, message_id=call.message.message_id)
    markup = types.InlineKeyboardMarkup(row_width=1)
    markup.add(*buttons)
    bot.send_message(call.message.chat.id,
                     text="Близкий друг Онегина и яркая его противоположность. Это пылкий, восторженный молодой человек, не знавший жизни и не ведавший предательства. Однолюб, поэт-романтик, он искренне верит в дружбу, любовь, справедливость. Страстно влюблён в Ольгу Ларину, которой посвящает свои стихи. Погибает от руки Онегина на дуэли.", reply_markup=markup)

@bot.callback_query_handler(func=lambda call: call.data == 'four')
def five(call):
    bot.delete_message(chat_id=call.message.chat.id, message_id=call.message.message_id)
    markup = types.InlineKeyboardMarkup(row_width=1)
    markup.add(*buttons)
    bot.send_message(call.message.chat.id,
                     text="Жизнерадостная, беззаботная, весёлая девушка, образ которой, впрочем, не отличается глубиной. Голубые глаза и льняные волосы юной кокетки пленяют сердце Ленского. Ветреное поведение Ольги становится причиной дуэли между Онегиным и Ленским. Она недолго горюет после трагической смерти возлюбленного и вскоре удачно выходит замуж за офицера.", reply_markup=markup)

@bot.callback_query_handler(func=lambda call: call.data == 'five')
def six(call):
    bot.delete_message(chat_id=call.message.chat.id, message_id=call.message.message_id)
    markup = types.InlineKeyboardMarkup(row_width=1)
    markup.add(*buttons)
    bot.send_message(call.message.chat.id,
                     text="Добрая, заботливая, все свои силы направляющая на воспитание детей и ведение хозяйства. В молодости она мечтала о возвышенной любви, и её прекрасная головка была полна романтических иллюзий. Однако после замужества, переезда в деревню и    рождения дочерей восторженные фантазии и мечтательность молодой женщины сошли на нет. Она смогла приспособиться к реалиям новой жизни и научилась ловко управлять супругом.", reply_markup=markup)

@bot.callback_query_handler(func=lambda call: call.data == 'six')
def seven(call):
    bot.delete_message(chat_id=call.message.chat.id, message_id=call.message.message_id)
    markup = types.InlineKeyboardMarkup(row_width=1)
    markup.add(*buttons)
    bot.send_message(call.message.chat.id,
                     text="Молодость героя была весьма бурной и весёлой. Несмотря на положение холостяка, у Зарецкого есть незаконнорождённые дети от крепостных крестьянок. Это неглупый, острый на язык человек, но вместе с тем холодный и безразличный. Во время дуэли выступает в роли секунданта Владимира Ленского.", reply_markup=markup)

@bot.callback_query_handler(func=lambda call: call.data == 'seven')
def eight(call):
    bot.delete_message(chat_id=call.message.chat.id, message_id=call.message.message_id)
    markup = types.InlineKeyboardMarkup(row_width=1)
    markup.add(*buttons)
    bot.send_message(call.message.chat.id,
                     text="Богатый и знатный генерал, дворянин. Вся его жизнь связана со служением Отечеству. Во время войны он был серьёзно ранен, но это не стало для него поводом уйти на покой. Он трепетно относится к Татьяне и ради её счастья готов на многое. И, хотя Ларина не любит мужа, она остаётся ему верна и отвергает Онегина.", reply_markup=markup)

@bot.callback_query_handler(func=lambda call: call.data == 'eight')
def nine(call):
    bot.delete_message(chat_id=call.message.chat.id, message_id=call.message.message_id)
    markup = types.InlineKeyboardMarkup(row_width=1)
    markup.add(*buttons)
    bot.send_message(call.message.chat.id,
                     text="Княжна Алина проживает в Москве, в одиночестве — у неё нет своих детей, она никогда не была замужем. Когда Татьяна с матерью приезжает в столицу на «ярмарку невест», они останавливаются в её доме.", reply_markup=markup)

@bot.callback_query_handler(func=lambda call: call.data == 'nine')
def ten(call):
    bot.delete_message(chat_id=call.message.chat.id, message_id=call.message.message_id)
    markup = types.InlineKeyboardMarkup(row_width=1)
    markup.add(*buttons)
    bot.send_message(call.message.chat.id,
                     text="Филипьевна — добрая старушка с чутким сердцем, долгое время служившая в доме Лариных. Она часто рассказывает своей воспитаннице увлекательные истории из жизни, всячески опекает и мягко наставляет её.", reply_markup=markup)


@bot.message_handler(content_types=['photo'])
def photo(call):
        bot.reply_to(call.message,
                     'К сожалению я ещё не умею обрабатывать фото, но могу сказать что это фото очень красивое!')


@bot.message_handler(content_types=['video'])
def video(message):
        bot.reply_to(message,
                     text="К сожалению я ещё не умею обрабатывать видео, но могу сказать что это видео очень классное!")


bot.polling(none_stop=True)
