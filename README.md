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

### Instruccions d'automatització de la traducció de documents

Vegeu el repositori [xxai-art/doc](https://github.com/xxai-art/doc)

Es recomana instal·lar primer nodejs, [direnv](https://direnv.net) i [bun](https://github.com/oven-sh/bun) , i després executar `direnv allow` després d'entrar al directori.

Per tal d'evitar magatzems massa grans traduïts a centenars d'idiomes, vaig crear un magatzem de codi independent per a cada idioma i vaig crear una organització per emmagatzemar aquest magatzem.

Si configureu la variable d'entorn `GITHUB_ACCESS_TOKEN` i, a continuació, executeu [create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) , es crearà automàticament el magatzem.

Per descomptat, també el podeu posar en un magatzem.

Referència de l'script de traducció [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

El codi de l'script s'interpreta de la següent manera:

[bunx](https://bun.sh/docs/cli/bunx) és un reemplaçament de npx, que és més ràpid. Per descomptat, si no teniu bun instal·lat, podeu utilitzar `npx` .

`bunx mdt zh` representa `.mdt` al directori zh com `.md` , vegeu els 2 fitxers enllaçats a continuació

* [coffee_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [coffee_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` és el codi bàsic per a la traducció (si només teniu `nodejs` instal·lat, però `bun` i `direnv` no estan instal·lats, també podeu executar `npx i18n` per traduir).

Analitzarà [i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) , la configuració d' `i18n.yml` en aquest document és la següent:

```
en:
zh: ja ko en
```

El significat és: traducció del xinès al japonès, coreà, anglès, traducció a l'anglès a tots els altres idiomes. Si només voleu donar suport al xinès i l'anglès, només podeu escriure `zh: en` .

L'últim és [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) , que extreu el contingut entre el títol principal i el primer subtítol del `README.md` de cada idioma per generar una entrada `README.md` . El codi és molt senzill, podeu mirar-lo vosaltres mateixos.

L'API de Google s'utilitza per a la traducció gratuïta. Si no podeu accedir a Google, configureu i configureu un servidor intermediari, com ara:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

L'script de traducció generarà una memòria cau de traducció al directori `.i18n` , comproveu-lo amb `git status` i afegiu-lo al dipòsit de codi per evitar traduccions repetides.
