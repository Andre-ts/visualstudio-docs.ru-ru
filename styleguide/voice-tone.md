# <a name="voice-and-tone-guidelines"></a>Рекомендации по стилю

С помощью ваших документов разработчики будут знакомиться с возможностями .NET Core, чтобы применять их в своей повседневной работе.
Ваша цель — создавать полезные статьи, которые помогут читателям в освоении технологий. Наши рекомендации соответствуют этой цели. Руководство по стилю содержит четыре рекомендации:
- [Используйте естественный стиль речи](#use-a-conversational-tone)
- [Используйте форму обращения к читателю](#write-in-2nd-person)
- [Используйте действительный залог](#use-active-voice)
- [Пишите на уровне, доступном ученикам средних классов](#target-a-fifth-grade-reading-level)

В процессе чтения руководства вам встретятся примеры применения этих рекомендаций. При написании руководства мы следовали этим рекомендациям, чтобы показать вам, как следует создавать документацию по .NET Core. Мы также привели обратные примеры, чтобы увидели, как будут выглядеть статьи, если не следовать этим правилам.

## <a name="details-on-each-guideline"></a>Сведения о каждой рекомендации

### <a name="use-a-conversational-tone"></a>Используйте естественный стиль речи
#### <a name="appropriate-style"></a>Правильный стиль
Мы хотим, чтобы документация имела разговорный стиль. Когда вы читаете учебник или пояснение, у вас должно возникать ощущение диалога с автором.
Поэтому статьи должны быть естественными и содержательными. Когда вы читаете документ, вам должно казаться, что автор объясняет вам материал.

#### <a name="inappropriate-style"></a>Неправильный стиль
Естественный разговорный стиль значительно отличается от используемого при формальном описании технических вопросов. Такие статьи очень полезны, но они характеризуются стилем, сильно отличающимся от принятого в нашей документации. При написании научных журналов интонация и стиль речи иные.
Возникает ощущение, что читаешь сухой отчет по неинтересной теме.  

В первом абзаце выше соблюдается рекомендация касательно естественного стиля. Во втором стиль более академичный. Разница чувствуется сразу. 

### <a name="write-in-second-person"></a>Используйте форму обращения к читателю
#### <a name="appropriate-style"></a>Правильный стиль
Вам необходимо писать статьи так, как будто вы обращаетесь напрямую к читателю. Вам следует часто использовать обращение во втором лице (как в этих двух предложениях). Обращение во втором лице не обязательно означает использование местоимения "вы". Обращайтесь к читателю. Используйте повелительное наклонение.
Сообщайте читателю, чему вы хотите его научить.

#### <a name="inappropriate-style"></a>Неправильный стиль 
Автор также может писать статьи в третьем лице. При таком подходе автору необходимо подбирать какие-либо местоимения или существительные для обращения к читателю. Читателю такой стиль может казаться отстраненным и менее увлекательным.

В первом абзаце используется рекомендованный стиль. В третьем применяется стиль в третьем лице. Используйте форму обращения к читателю. Как вы, возможно, заметили, такой стиль воспринимается легче.

### <a name="use-active-voice"></a>Используйте действительный залог

Пишите статьи в действительном залоге. Действительный залог означает, что подлежащее в предложении указывает на то, кто выполняет действие, выраженное сказуемым. Для сравнения в страдательном залоге предложение строится так, что действие направлено на подлежащее. Сравните следующие два примера.

>Компилятор преобразовал исходный код в исполняемый файл.

>Исходный код был преобразован в исполняемый файл компилятором.

В первом предложении используется действительный залог. Второе было написано в страдательном залоге.
(Эти два предложения также служат примерами каждого стиля.)

Мы рекомендуем действительный залог, так как он проще для восприятия. Страдательный залог может делать текст более трудным для чтения.

### <a name="target-a-fifth-grade-reading-level"></a>Пишите на уровне, доступном ученикам средних классов

Эта последняя рекомендация связана с тем, что многие наши читатели не являются носителями языка, на котором пишутся статьи.
Материалы предназначены для людей из самых разных стран мира. Их словарный запас может быть меньше вашего.

Тем не менее, вы пишете для технических специалистов. Поэтому предполагается, что ваши читатели имеют навыки программирования и владеют специальной терминологией. Объектно-ориентированное программирование, класс, объект, функция, метод, — все эти термины должны быть им знакомы. Однако не у каждого читателя есть диплом специалиста по информатике. Если вы используете такие термины, как, например, "идемпотентный", то, вероятно, следует объяснять их значение:

>Метод Close() является идемпотентным, то есть вы можете вызывать его несколько раз, но результат будет таким же, как если бы вы вызвали его один раз.