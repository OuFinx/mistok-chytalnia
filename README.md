# Читальня «Містка»

[English](#in-english)

![Читальня «Містка»](.github/media/hero.jpg)

Як шукати, перевіряти й читати архівні джерела разом із мовною моделлю. Скіли для Claude Code, методики й матеріали, напрацьовані в роботі над сайтом [«Місток»](https://mistok.wiki).

**Тут немає порад.** Кожне правило або коштувало зіпсутого прогону, або виміряне числом, і число стоїть поруч із правилом.

## Поставити

```bash
git clone https://github.com/OuFinx/mistok-chytalnia.git
ln -s "$PWD/mistok-chytalnia/skills/metryky" ~/.claude/skills/metryky
```

Символьне посилання зручніше за копію: `git pull` оновлює скіл на місці. Так само для решти скілів. Далі вони підхоплюються самі, коли ви просите прочитати скан або звірити текст із джерелами.

## Скіли

| | Про що | Найдорожче з того, що всередині |
|---|---|---|
| [**metryky**](skills/metryky/SKILL.md) | Метричні книги й акти ЗАГС: де взяти справу, як прочитати аркуш, як записати прочитане | Одна сторінка = один агент. Агент, що прочитав тринадцять сторінок підряд, коштував 251 тисячу токенів, а три сусідні вмерли на ліміті, не записавши нічого |
| [**zvirka**](skills/zvirka/SKILL.md) | Звірка написаного проти джерел: чи джерело каже саме це, чи виноска стоїть на потрібному реченні | Вікно навколо слів твердження **завжди** містить те, що шукали, тому «не знайшов» неможливо відрізнити від «джерело цього не каже» |
| [**presa**](skills/presa/SKILL.md) | Стара періодика: ключі пошуку, вирізки замість шпальт, чотири тихі поломки OCR | З восьми написань назви села матеріал дала рівно одна форма. До того село пів року стояло як «у пресі порожньо» |
| [**rozvidka**](skills/rozvidka/SKILL.md) | Розвідка кількома агентами: ексклюзивні зони, ракурси, стелі викликів, бюджет | Ділити треба за джерелами, а не за темами: сім агентів по семи джерельних зонах не перетнулися жодного разу |

## Матеріали

| | Про що |
|---|---|
| [**pastky.md**](materials/pastky.md) | Двадцять три пастки архівного пошуку. Джерело, яке бреше про себе; пошук, який мовчить замість заперечувати; скан, на якому око бачить іншу неправду; перевірка, яка все пропустила |
| [**htr.md**](skills/metryky/references/htr.md) | Чому автоматичне читання рукопису поки що не працює, з арифметикою порогу. Варте читання, навіть якщо метрики вам байдужі |

## Матеріали до пошуку

| | Що всередині |
|---|---|
| [**pokazhchyky/**](pokazhchyky/) | Де в справі чи томі лежить ваше село: ревізькі казки Київського повіту 1795-1834 років по пʼятьох справах ДАКО, зміст і покажчик «Історії міст і сіл» 1971 року по всій Київщині, люди макарівського розділу поіменно. У `tsv`, відкривається таблицею |
| [**dzherela/**](dzherela/) | Бібліографія «Містка»: 564 джерела з архівними адресами й посиланнями, одним файлом |
| [**teksty/**](teksty/) | Розпізнаний текст двадцяти видань до 1917 року й довідника 1947 року, щоб шукати прізвище чи село, а не гортати скан |

Це росте з кожним селом: що і коли додалося, записано в [`ZMINY.md`](ZMINY.md).

## Приклад

[Один аркуш, прочитаний за цим скілом](examples/posimeinyi-spysok/): ось [фото](examples/posimeinyi-spysok/skan.jpeg), ось [що вийшло](examples/posimeinyi-spysok/prochytannia.md). Замовлення було «прочитай метрику», а перше, що дав прохід, - це не метрична книга, а посімейний список ревізького типу.

## Це не лише для Claude Code

Скіл це markdown, а не код. Порядок роботи, пастки й числа однаково читаються людиною й однаково кладуться в будь-який інший інструмент. Команди в текстах загальні (`pdftotext`, `pdfimages`, `pdftoppm`), ставити нічого не треба.

## Ліцензія

[MIT](LICENSE). Беріть, копіюйте, переробляйте під себе, вставляйте у свої скіли й проєкти, робіть що завгодно - питати дозволу не треба. Єдина умова MIT - зберігати текст ліцензії в копіях.

Єдине прохання, і воно не юридичне: згадуйте час від часу [«Місток»](https://mistok.wiki) :)

## In English

Methods for finding, reading and fact-checking archival sources together with a language model: Claude Code skills and reference material built while researching [Mistok](https://mistok.wiki), a Ukrainian local-history site.

Mistok currently covers 42 villages of the Makariv district (Kyiv oblast): 8,876 parish-register records, 116 biographies and 550 cited sources, with a footnote on every sentence. To see what a skill actually produces, here is [one page read with metryky](examples/posimeinyi-spysok): the [scan](examples/posimeinyi-spysok/skan.jpeg) and [the result](examples/posimeinyi-spysok/prochytannia.md).

There is no generic advice here. Every rule either cost a broken run or was measured, and the number sits next to the rule. For example, one agent that read thirteen register pages in a row burned 251k tokens while three neighbouring agents hit the limit without writing anything, hence the rule "one page, one agent".

- **metryky** - reading parish registers and civil registry acts from scans: where to find the file, how to read a page, how to record what was read.
- **zvirka** - checking a finished text against its sources: does the source say exactly this, and is the footnote on the right sentence.
- **presa** - searching digitized old newspapers: search keys across word forms and pre-reform spelling, clippings instead of full pages, silent OCR failures.
- **rozvidka** - splitting research across parallel agents: exclusive source zones, call ceilings, where the budget actually goes.
- **[pastky.md](materials/pastky.md)** - twenty-three pitfalls of archival search.
- **[pokazhchyky/](pokazhchyky/)**, **[dzherela/](dzherela/)**, **[teksty/](teksty/)** - finding aids (which file and page holds which village in the 1795-1834 revision lists and in the 1971 regional history volume), the full bibliography behind the site, and OCR text of pre-1917 books to search by surname or village. Grows with every village, see [ZMINY.md](ZMINY.md).

The skills are plain Markdown written in Ukrainian, so they work with any tool, not only Claude Code. Licensed under [MIT](LICENSE).
