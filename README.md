<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

# xxAI.art

Part del codi del lloc web és de codi obert, benvingut per ajudar a optimitzar la traducció.

## codi frontal

* [codi frontal](https://github.com/xxai-art/web)
* [Paquets d'idiomes per al lloc en conjunt](https://github.com/xxai-art/web/tree/main/i18n)
* [Paquets d'idioma per als mòduls d'inici de sessió](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Web Documentació multilingüe](https://github.com/xxai-doc)

El llenguatge de programació frontal és [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , que afegeix algunes funcions basades en la sintaxi del coffeescript, vegeu [./coffee_plus.md](./coffee_plus.md) .

## Internacionalització de llocs web i documents

A partir dels 3 projectes següents

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  El sufix és `.mdt` , podeu utilitzar la sintaxi semblant a `<+ ./coffee_plus/import.js>` per fer referència a fitxers externs i generar una reducció amb el sufix `.md` .

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  La traducció Markdown no traduirà codis i enllaços, i guardarà a la memòria cau les frases traduïdes. Si es modifica la traducció però no es modifica el text original, executar-la de nou no sobreescriurà la modificació de la traducció.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  Fitxers d'idioma per traduir llocs web generats `yaml` .
