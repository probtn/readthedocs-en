.. probtn documentation master file, created by
   sphinx-quickstart on Mon Nov  2 12:32:08 2015.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

.. _webparams:
  
Params description
==================================

Description of the parameters used by the button (by application)
 
If a parameter is used differently in different modes, it is specifically marked (including, the required modes)


MenuTemplateVariant
----------------------------------

This param is used to select nessesary variant of menu apperiance
(used then ButtonType==menu)

Possible options:
* list - default template, list
* radialcorner - partical radial menu (button is in the corner, and menu items aore located in one between 0 and 90 degrees)

VideoType
----------------------------------
Video type used in button

Options:
* mp4 - by default
* youtube - video from youtube

Debug
----------------------------------
The debug mode of the button displays the version of the button enabled by an open fancybox.

By default:
* false

UseGeoLocation
----------------------------------
Use or not the data on the geographical position of a user

By default:
* false

WaitForGeoLocation
----------------------------------
With geolocation on, wait for the positioning data to be received (and user's permission in case of the first use) before the display of the button.

By default:
* false

loadJqueryPepJS
----------------------------------

Download jquery.pep.js if the script does not find the appropriate library function

By default:
* true

loadFancyboxJS
----------------------------------
Download fancybox if the script does not find the appropriate library function

By default:
* true

DisableButtonMove
----------------------------------
Disable button move

By default:
* false

waitForIframeButtonLoaded
----------------------------------
Wait for the content of the button iframe to be uploaded.

By default: 
* true

ButtonIframeInitialSize
----------------------------------
Button size. Set as an object ``{ W: 0, H: 0 }``
here W and H stand for width and height in px respectively.

If the values are set to 0, scaling for the button iframe is not needed.
 
If positive values are set, the iframe is adjusted to the size indicated in the ButtonSize parameter respectvely.

ButtonImageType
----------------------------------
Type of the button content. By default: image

Options:
* image
* iframe

ClickOnCloseButton
----------------------------------
Close the button by a click on it.
By default: true

AlwaysShowCloseButton
----------------------------------
Always show the closing area.
By default: false

FullscreenClickLink
----------------------------------
(For the mode when ButtonType=='fullscreen')
Click on fullscreen will open link.

HideWithoutInteractionTime
----------------------------------
By default: 0  (not hide).
Period of time before the button hides when no interaction is in place.

cssEaseDuration
----------------------------------
Animation duration (in ms) for jquery.pep
By default: 300

ChangeScrollButtonAtFullSiteHeight
----------------------------------
Change the button view in the scroll mode based on the page height (true) or the window size (false)

ControlInIframeFromParent
----------------------------------
Is button control from the parent.
By default: false

isAddUtmSource
----------------------------------
Add the utm_source parameter to ContentURL.
By default: false

UtmSourceUseOnlyDomain
----------------------------------
By default false.
 
Use utm_source by default. If set to false, the full URL is used, if set to true, only the domain is used.

UtmCampaign
----------------------------------
Value of the  utm_campaign parameter. Not set if the field is left blank,
By default ""

UtmSource
----------------------------------
Value of the utm_source parameter,  if the field is left blank, the current page URL (or domain, defined by the UtmSourceUseOnlyDomain attribute) is used.
By default ""

IframeScale
----------------------------------
parameter applied to the iframe for transform: scale(value)
 
By default: 1.

If iframeScaleMinWidth !=0, calculations are made based on this parameter

ButtonInitDelay
----------------------------------
Delay before the button display (in ms)
By default: 0

VideoClickURL
----------------------------------
Link that a user opens by a click on the video. (If VideoClickURL =='', a line from VideoPoster is pasted. If the parameter is left blank, no need to add a link to the video.

ButtonOnClick 
----------------------------------
Event called by a click on the button (added in an onclick, necessary to play a video in mobile browsers)
 
By default:

```function start1() { var video = $("#video").get(0); video.play(); }; start1(); setTimeout(start1 , 1500);```

ButtonType 
----------------------------------
Button type
 
By default 
button - button behaviour by default
 
Current options for ButtonType
* •	button - button with an iframe in fancybox
* menu - floating menu mode
* smartbanner - smartbanner display
* fullscreen -  autoplay of the content after script initialization
* button_and_active_zones - button and active zones
* button_and_scroll_zones - button and changing images or different images in different screen zones (by height)
* fullscreen_fancybox - autoplay of the content in fanncybox after script initialization


ButtonContentType
----------------------------------
Type of the button content
 
By default: 
* iframe - page display in the iframe
 
Current options for ButtonContentType

* iframe - page display in the iframe
* video - video play
* anchor - transition to an indicated anchor on the page (ContentURL is a full link or an anchor on the page, e.g., in #someAnchor), the transition to an anchor or a link happens in the same tab\window.

VideoSize
----------------------------------
Video size (necessary to adjust the size of the video for mobile browsers that for some reason do not keep video porportions)
 
The parameter itself is an object that consists of X and Y attributes (width and height)

Example (value by default):

``VideoSize: { X: 1920, Y: 1080 }````

VideoPoster
----------------------------------
Poster for the video.
Value is URL (to the image).


TrackingLink
----------------------------------
Link to the image to be used as background for the button wrapper. Introduced in order to set one's image (pixel) to collect statistical data about a user.

MinimizeWrapperTime
----------------------------------
Period of time before the size of the button wrapper gets smaller. Introduced to fix the bugs in animation that sometimes appear on mobile devices.

OpenExternal
----------------------------------
Параметр, отвечающий за то, как именно должна открываться ссылка (соответственно для ```ButtonType = button``` )
Parameter that defines how link would be opened (for ```ButtonType = button``` )

* false - содержимое открывается в fancybox
* true - контент открывается в новой вкладке (применяется в случае, если сайт не может быть показан в iframe по тем или иным причинам)

CampaignID
----------------------------------
Campaign identifier

NeverClose
----------------------------------
If set to true, removes the closing area for the button
 
Aplied when ```ButtonType = button```

domain
----------------------------------
Domain that requests button settings. If left blank, the domain is received automatically and corresponds to the domain where the button is activated.
 
If a certain domain is indicated, the actual domain is not used and the settings for the indicated domain are received.

fancyboxJsPath
----------------------------------
URL to the location of the fancybox library.  

fancyboxCssPath
----------------------------------
URL to the location of fancybox css.

jqueryPepPath
----------------------------------
URL to the location of library jquery.pep

buttonAnimationTimeAfterFancybox
----------------------------------
Animation duration after fancybox is closed, in ms

HideAfterFirstShow
----------------------------------
Show or not the button after its first display to a user.
* true - button hides after the first display (until HideAfterFirstShow is set to true or the cookie expires)
* •	false -  button is displayed every time (defined by server settings and server targeting)
 
Applied when ButtonType = button

LoadFancyboxCSS
----------------------------------
Download or not css for fancybox by default.
* true - download
* false - don't download (e.g., fancybox is already in use on the site)

ContentURL
----------------------------------
URL to the content displayed by the button.

For different ButtonContentType:
* iframe - any link to the site or another content displayed in the iframe
* video - сlink to the video (supported by HTML5 video)

ButtonEnabled
----------------------------------
Enabled/disabled

ButtonVisible
----------------------------------
Visible/invisible
 
ButtonPosition
----------------------------------
Button position. Set as an object ```{X:0.5, Y:.5}```
where X and Y vary between 0 and 1 (1 stands for width or height respectively).
Applied when ```ButtonType = button```

ButtonSize
----------------------------------
Button size. Set as an object ```{ W: 64.0, H: 64.0 }```
where W and H stand for width and height in px respectively.
 Applied when  ```ButtonType = button```


ButtonDragSize
----------------------------------
Size of the button when dragged. Set as an object. ```{ W: 64.0, H: 64.0 }```
where W and H stand for width and height in px respectively
 
Applied when ```ButtonType = button```

ButtonOpacity
----------------------------------
Button opacity. Varies between 0 and 1 (0 - transparent, 1 – opaque)
Applied when ```ButtonType = button```

ButtonDragOpacity
----------------------------------
Opacity of the button when dragged
Applied when ```ButtonType = button```

ButtonImage
----------------------------------
Link to the button image
Applied when ```ButtonType = button```

ButtonDragImage
----------------------------------
Link to the image of the button when dragged
Applied when ```ButtonType = button```

ClosePosition
----------------------------------
Position of the button closing area
 
Set as an object ```{X:0.5, Y:0.5}```
where X and Y vary between 0 and 1 (1 stands for window width or height respectively)
 
Applied when ```ButtonType = button```
 
CloseSize
----------------------------------
Size of the closing area. Set as an object ```{ W: 64.0, H: 64.0 }```
where W and H stand for width and height in px respectively
 
Applied when ```ButtonType = button```

CloseActiveSize
----------------------------------
Size of the closing area in active mode (when the button is rolled over the closing area).
Set as an object ```{ W: 64.0, H: 64.0 }```
where W and H stand for width and height in px respectively

Applied when ```ButtonType = button```

CloseOpacity
----------------------------------
Opacity of the closing area.
Applied when ```ButtonType = button```

CloseActiveOpacity
----------------------------------
Opacity of the closing area in active mode (when the button is rolled over it).
 
Applied when ```ButtonType = button```

CloseImage
----------------------------------
Link to the image for the closing area.
 
Applied when ```ButtonType = button```

HintLabelInsets
----------------------------------
Text insets (below the button line)
 
Set in the following format ```{ T: 4.0, B: 4.0, L: 4.0, R: 4.0 }```
 
Applied when ```ButtonType = button```

HintText
----------------------------------
Button hint text
Applied when ```ButtonType = button```

HintFont
----------------------------------
Font parameters for the buttonhint text
Set as an object ```{ Family: "Arial", Size: 18 }```

* Family - шрифт для надписи. Указывается для font-family
* Size - размер текста

Applied when ```ButtonType = button```

HintFontColor
----------------------------------
Text color. Set as an object ```{ R: 1.0, G: 1.0, B: 1.0, A: 1.0 }```
Applied when ```ButtonType = button```

VendorText
----------------------------------
Vendor text (displayed at the bottom of fancybox)

VendorSite
----------------------------------
Link to the vendor's site

VendorTextFont
----------------------------------
Format corresponds to the HintFont parameter

VendorTextColor
----------------------------------
VendorText color. Format corresponds to HintFontColor

VendorColor
----------------------------------
VendorText background color

iframeScaleMinWidth
----------------------------------
Minimal width for the site displayed inside the iframe. If the current fancybox width is smaller than the required iframeScaleMinWidth, the iframe is to be scaled using the tranform parameter to fit in the current width.
 
Suitable for the sites that do not adjust autmatically to the given width.
 
Be default 0, no need to scale.

iframeScale
----------------------------------
By default 1. Scaling attribute for the transform parameter of the iframe.
 
Calculated automatially based on iframeScaleMinWidth and fancybox width.

HintOpacity
----------------------------------
Text opacity. (from 0 to 1)
Applied when ```ButtonType = button```

HintImage
----------------------------------
Background image for the button signing.
Applied when ```ButtonType = button```

ContentSize
----------------------------------
Fancybox size

Set as an object ```{ W: 100, H: 100, X: "90%", Y: "90%" }```
 
If IsManualSize = true, X and Y show up for the size in %.
Otherwise, W and H are used (width and height respectively)


IsManualSize
----------------------------------
If IsManualSize = true, ContentSize shows X and Y for the size in %.
 
Otherwise, W and H are used (width and height in px respectively)

ContentInsets
----------------------------------
Insets for fancybox (and its substitutes)
 
Set as an object ```{ T: -2.0, B: -2.0, L: -2.0, R: -2.0 }```
 
With given top, bottom, left and right insets.
If ContentInsets is below 0, insets are calculated automatically based on the button size.

HideInFrame
----------------------------------
Parameter defining whether to display the button when the page opens in the iframe.

* true -  hide the button when the page opens in the iframe
* false - display the button when the page opens in the iframe

ZCustomCss
----------------------------------
По умолчанию "".
В случае, если в данном параметре присутствует текст, он будет добавлен как css в страницу.
Параметр нужен, если необходимо модифицировать css страницы без вмешательства в код.

showInParent
----------------------------------
По умолчанию false
Если кнопка находится в iframe и родительское окно как и старница в iframe размещены на одном и том же домене, то при true кнопка добавить в родителя код //cdn.probtn.com/includepb.min.js для запуска кнопки в родителе.

isHPMD
----------------------------------
По умолчанию false
В случае, если установлено в true, то будут вызываться события HPMD 

dfp
----------------------------------
Объект для настроек при использовании DFP Google
dfp: { isDFP: false,  clickUrlEsc: "", cacheBuster: ""}
isDFP - используется ли DFP
clickUrlEsc - ссылка из макроса DFP для отслеживания кликов

ClickCounterLink
----------------------------------
Ссылка вызываемая при нажатии на кнопку. Необходима для случаев, когда требуется сторонний подсчет статистики (в частности кликов по кнопке) - для данной ссылки производится ajax запрос

isServerCommunicationEnabled
----------------------------------
По умолчанию true
Параметр отвечает за то, включено ли взаимодействие с сервером (в частности получение настроек и отправку статистики).

useLocalFileSettings
----------------------------------
По умолчанию false
Использовать ли json файл с настройками кнопки

localSettingsPath
----------------------------------
Url (абсолютный или относительный) до json файла 
По умолчанию "settings.json"

isSmartBanner
----------------------------------
По умолчанию false
Если true, то вместо кнопки будет показываться смартбаннер (на основе https://github.com/jasny/jquery.smartbanner )

smartbannerJsPath
----------------------------------
Путь по умолчанию до jquery.smartbanner.js
'//cdn.probtn.com/libs/jquery.smartbanner.js',

smartbannerCssPath
----------------------------------
Путь по умолчанию до jquery.smartbanner.css
      '//cdn.probtn.com/libs/jquery.smartbanner.css',

smartbanner
----------------------------------
Объект с настройками для smartbanner'a

Настройки по умолчанию
:: 
	{
	  iosAppId: null,
	  androidAppId: null,
	  isFixed: false, //if true, smartbanner will have position: fixed style
	  isFixedMode: 'default', //default - position fixed over content
	  // extrusion - banner is fixed, but content moved down (banner height) - so banner don't close any content at page
	  
	  title: null, // What the title of the app should be in the banner (defaults to <title>)
	  author: null, // What the author of the app should be in the banner (defaults to <meta name="author"> or hostname)
	  price: 'FREE', // Price of the app
	  appStoreLanguage: 'us', // Language code for App Store
	  inAppStore: 'On the App Store', // Text of price for iOS
	  inGooglePlay: 'In Google Play', // Text of price for Android
	  inAmazonAppStore: 'In the Amazon Appstore',
	  inWindowsStore: 'In the Windows Store', // Text of price for Windows
	  GooglePlayParams: null, // Aditional parameters for the market
	  icon: null, // The URL of the icon (defaults to <meta name="apple-touch-icon">)
	  iconGloss: null, // Force gloss effect for iOS even for precomposed
	  url: null, // The URL for the button. Keep null if you want the button to link to the app store.
	  button: 'VIEW', // Text for the install button
	  scale: 'auto', // Scale based on viewport size (set to 1 to disable)
	  speedIn: 300, // Show animation speed of the banner
	  speedOut: 400, // Close animation speed of the banner
	  daysHidden: 15, // Duration (in days) to hide the banner after being closed (0 = always show banner)
	  daysReminder: 90, // Duration (in days) to hide the banner after "VIEW" is clicked *separate from when the close button is clicked* (0 = always show banner)
	  force: null, // Choose 'ios', 'android' or 'windows'. Don't do a browser check, just always show this banner
	  hideOnInstall: true, // Hide the banner after "VIEW" is clicked.
	  layer: false, // Display as overlay layer or slide down the page
	  iOSUniversalApp: true // If the iOS App is a universal app for both iPad and iPhone, display Smart Banner to iPad users, too.      
	  appendToSelector: 'body' //Append the banner to a specific selector
	}

MainButtonClickable
----------------------------------
Можно ли нажать на основную кнопку, по умолчанию true

Menu параметры
----------------------------------
Использование scroll-зон возможно в случае если ButtonType=="menu"

MenuItems
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Массив с объектами, описывающими scroll зоны

Описание объекта из MenuItems

Text
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Текст пункта меню

ActionURL
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Ссылка для перехода по нажатию на пункт меню

Image
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Картинка пункта меню

Name
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Уникальное название пункта меню (для статистики)

Type
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Тип пункта меню. По умолчанию external
Варианты:
* external
* video
* iframe

MenuOptions
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Объект с описанием основных свойств меню

FontSize
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Размер шрифта пункта меню

FontFamily
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Шрифт для пункта меню

BackgroundColor
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Цвет фона пункта меню

ForegroundColor
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Цвет текста пункта меню

MenuHeight
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Высота пункта меню

Пример объекта:
::
        MenuOptions: {
            FontSize: "1.4em",
            FontFamily: '"Helvetica Neue",Helvetica,Arial,"Lucida Grande",sans-serif',
            BackgroundColor: 'rgba(49,55,61,.95)',
            ForegroundColor: '#fff',
            MenuHeight: "3.4em"
       }

Scroll параметры
----------------------------------
Использование scroll-зон возможно в случае если ButtonType=="button_and_scroll_zones"

ScrollZones
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Массив с объектами, описывающими scroll зоны

Описание объекта из ScrollZones

ZoneHeight
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Высота зоны (полная высота страницы = 1)

ButtonImage
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Url картинки кнопки

ButtonDragImage
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Url картинки кнопки при перетаскивании

HintText
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Текст для картинки

TrackingLink
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Url для сбора статистики (при клике на кнопку)

CustomButtonParams
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Использовать ли дополнительные параметры для кнопки (размеры, прозрачность, etc.)
По умолчанию false

ButtonSize
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Размер кнопки. Задается как объект { W: 64.0, H: 64.0 }
Где W и H соответственно ширина и высота в px

ButtonDragSize
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Размер кнопки во время перетаскивания. Задается как объект { W: 64.0, H: 64.0 }
Где W и H соответственно ширина и высота в px

ButtonOpacity
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Прозрачность кнопки. Задается от 0 до 1 (0 - полностью прозрачна, 1 - не прозрачна)

ButtonDragOpacity
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Прозрачность при перетаскивании кнопки

Пример
::
ScrollZones: [
                        {
                           ZoneHeight: 0.5,
                           ButtonImage: "//cdnjs.cloudflare.com/ajax/libs/probtn/1.0.0/images/probtn/gray.png",
                           ButtonDragImage: "",
                           HintText: "",
                           TrackingLink: "",
                           CustomButtonParams: false,
                        ButtonSize: { // Размер
                            W: 64.0,
                            H: 64.0
                        },
                        ButtonDragSize: { // Размер при перемещении
                            W: 68.0,
                            H: 68.0
                        },
                        ButtonOpacity: 0.8, // Прозрачность
                        ButtonDragOpacity: 1.0 // Прозрачность при перемещении
                        },
                        {
                           ZoneHeight: 0.5,
                           ButtonImage: "//cdnjs.cloudflare.com/ajax/libs/probtn/1.0.0/images/probtn/gray.png",
                           ButtonDragImage: "",
                           HintText: "",
                           TrackingLink: "",
                           CustomButtonParams: false,
                        ButtonSize: { // Размер
                            W: 64.0,
                            H: 64.0
                        },
                        ButtonDragSize: { // Размер при перемещении
                            W: 68.0,
                            H: 68.0
                        },
                        ButtonOpacity: 0.8, // Прозрачность
                        ButtonDragOpacity: 1.0 // Прозрачность при перемещении
                        }
                    ]

ActiveZones параметры
----------------------------------
Использование активных зон возможно в случае если ButtonType=="button_and_active_zones"

ActiveZones
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Массив с объектами, описывающими активные зоны

Описание объекта из ActiveZone

Name
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Уникальное название зоны (A-Za-z0-9)

ButtonImageType
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Тип содержимого кнопки. По умолчанию image
Варианты:
* image
* iframe

ButtonIframeInitialSize
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Размер кнопки. Задается как объект { W: 0, H: 0 }
Где W и H соответственно ширина и высота в px
В случае, когда значения равны нулю, для iframe кнопки не применяется "масштабирование".
Если указаны размеры, то iframe от этих размеров будет погонятся под размеры, указанные в ButtonSize параметре соответственно.

Position
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Объект, описывающий местоположение зоны.
Пример:
Position: { X: 0.1, Y: 0.1 }
Позиция указывается как число от 0 до 1 

ActiveImage
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Ссылка на изображение для активной зоны (при наведении кнопки)

InactiveImage
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Ссылка на изображение для неактивной зоны (по умолчанию, при отсутствии наведения на зону)

ActionURL
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Ссылка, которая будет открыта при "сбрасывании" кнопки на зону. В случае, если ActionURL=="" (пустая строка), то откроется ссылка указанная в ContentURL (показываемая при нажатии на кнопку)

VisibleOnlyInteraction
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
true/false
По умолчанию true
* В случае true активная зона показывается только во время взаимодействия с кнопкой (ее перемещения)
* В случае false активная зона видна всегда

ClickCounterLink
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
По умолчанию - false
Ссылка вызываемая при сбрасывании  кнопки на активную зону. Необходима для случаев, когда требуется сторонний подсчет статистики (в частности кликов по кнопке) - для данной ссылки производится ajax запрос

ActiveSize
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Размер зоны в активном состоянии
Представляет собой 
ActiveSize: { W: 64, H: 64 }
Где W - ширина, H - высота

InactiveSize
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Размер зоны в активном состоянии
Представляет собой 
InactiveSize: { W: 64, H: 64 }
Где W - ширина, H - высота

InactiveOpacity
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Прозрачность зоны в неактивном состоянии

ActiveOpacity
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Прозрачность зоны в активном состоянии

Пример
::
                    IsActiveZones: false,
                    ActiveZones: [
                        {
                            Name: "Area1",
                            Position: {
                                X: 0.1, 
                                Y: 0.1
                            },
                            ActiveImage: "//probtnexample1.azurewebsites.net/img/logo.png",
                            InactiveImage: "//admin.probtn.com/eqwid_btn_nonpress.png",
                            ActiveSize: {
                                W: 64, 
                                H: 64
                            },
                            InactiveSize: { 
                                W: 64, 
                                H: 64 
                            },
                            ActionURL: "http://m0rg0t.ru",
                            ClickCounterLink: "",
                            VisibleOnlyInteraction: true,
                        },
                        {
                            Name: "Area2",
                            Position: {
                                X: 0.6,
                                Y: 0.1
                            },
                            ActiveImage: "//probtnexample1.azurewebsites.net/img/logo.png",
                            InactiveImage: "//admin.probtn.com/eqwid_btn_nonpress.png",
                            ActiveSize: {
                                W: 64,
                                H: 64
                            },
                            InactiveSize: {
                                W: 64,
                                H: 64
                            },
                            ActionURL: "",
                            ClickCounterLink: "",
                            VisibleOnlyInteraction: false,
                            InactiveOpacity: 0.8,
                            ActiveOpacity: 1
                        }
                    ]

Неиспользуемые параметры
==============================
 
ContentWebViewInsets
-----------------------------
Не используется

BaseInsets
-----------------------------
не используется в текущей версии кнопки

ButtonOpenImage
-----------------------------
Не используется

ButtonInactiveImage
-----------------------------
Не используется

CloseActiveImage
-----------------------------
Не используется.
Ссылка на изображение для области закрытия в активном состоянии.

ButtonOpenSize
-----------------------------
Не используется.
Размер кнопки когда открыт fancybox. Задается как объект { W: 64.0, H: 64.0 }
Где W и H соответственно ширина и высота в px

ButtonInactiveSize
-----------------------------
Не используется.
Размер кнопки в неактивном состоянии. Задается как объект { W: 64.0, H: 64.0 }
Где W и H соответственно ширина и высота в px

HintInsets
-----------------------------
Не используется

ButtonOpenOpacity
-----------------------------
Не используется

ButtonInactiveOpacity
-----------------------------
Не используется

HintImageInsets
-----------------------------
Не используется

VendorOpacity
-----------------------------
Не используется

ContentImageInsets
-----------------------------
Не используется

ContentOpacity
-----------------------------
Не используется

ContentBackOpacity
-----------------------------
Не используется

ContentBackColor
-----------------------------
Не используется

ContentActivityColor
-----------------------------
Не используется

ContentImage
-----------------------------
Не используется

ContentArrowSize
-----------------------------
Не используется

ContentArrowOffset
-----------------------------
Не используется

ContentArrowImageT
-----------------------------
Не используется

ContentArrowImageB
-----------------------------
Не используется

ContentArrowImageL
-----------------------------
Не используется

ContentArrowImageR
-----------------------------
Не используется

HintArrowSize
-----------------------------
Не используется.

HintArrowOffset
-----------------------------
Не используется.

HintArrowImageT
-----------------------------
Не используется.

HintArrowImageB
-----------------------------
Не используется.

HintArrowImageL
-----------------------------
Не используется.

HintArrowImageR
-----------------------------
Не используется.

Остальные параметры
-----------------------------
DefaultDuration, DefaultDelay, OpenDuration, OpenDelay, CloseDuration, CloseDelay, ButtonShowDuration, ButtonShowDelay, ButtonHideDuration, ButtonHideDelay, ButtonDragDuration, ButtonDragDelay, ButtonUndragDuration: 0.2, ButtonUndragDelay, ButtonInactiveDuration, ButtonInactiveDelay, ButtonInertiaSpeed, ButtonInertiaSpeedMin, ButtonInertiaSpeedMax, ButtonInertiaFactor, CloseShowDuration, CloseShowDelay, CloseHideDuration, CloseHideDelay, CloseActiveDuration, CloseActiveDelay, CloseUnactiveDuration, CloseUnactiveDelay, HintLaunchDuration, HintLaunchDelay, HintShowDuration, HintShowDelay, HintHideDuration, HintHideDelay, ContentShowDuration, ContentShowDelay, ContentHideDuration, ContentHideDelay

Не используется
 
Параметры по умолчания для кнопки
=================================


