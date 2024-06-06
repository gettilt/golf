<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# Golf
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
The sport of Golf is taking off, rule changes are pushing faster rounds and the investments into new leagues, LIV Golf, are fueling more interest in the sport. Any companies related to Golf win.
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| AMZN | Amazon.com, Inc. will benefit from increased online sales of golf equipment and apparel. | chat_gpt,claude |
| DE | Deere & Company, through its John Deere brand, supplies golf course maintenance equipment, benefiting from increased golf course activity. | chat_gpt |
| DIS | The Walt Disney Company, through its ESPN network, will benefit from broadcasting more golf events. | chat_gpt,claude |
| GOLF | Acushnet Holdings Corp, the parent company of Titleist and FootJoy, stands to gain from higher demand for golf balls, clubs, and apparel. | chat_gpt,twitter,google,claude |
| MC | LVMH Moët Hennessy Louis Vuitton, through its TAG Heuer brand, produces luxury golf watches and accessories. | chat_gpt |
| NKE | Nike, Inc. produces golf apparel and footwear, benefiting from the sport's growing popularity. | chat_gpt,google,claude |
| VSTO | Vista Outdoor Inc. owns Bushnell Golf, a leading provider of golf rangefinders and GPS devices. | chat_gpt,google,claude |
| DKS | Dick's Sporting Goods is a major retailer of golf equipment and apparel in the United States. As golf participation increases, Dick's is likely to see higher sales in its golf segment, which includes clubs, balls, and accessories from various brands. | google,claude |
| MODG |  | google |
| GENI | Genius Sports Limited provides data and technology services to sports leagues, including the PGA Tour. As golf gains popularity, Genius Sports could benefit from increased demand for its data analytics and fan engagement solutions in the golf market. | claude |
| LULU | Lululemon Athletica is a premium athletic apparel company that has recently entered the golf market with its golf-specific clothing line. The company's focus on comfort, performance, and style could resonate with the growing number of golfers. | claude |
| TTWO | Take-Two Interactive Software, Inc. publishes the popular PGA Tour 2K video game series. As golf gains popularity, the company could benefit from increased sales of its golf video games, which offer realistic gameplay and licensed courses. | claude |
| UA | Under Armour is a sports apparel and footwear company that has been expanding its presence in the golf market. The company's golf apparel, designed for performance and comfort, may appeal to the growing number of golfers. | claude |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/golf/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/golf" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
