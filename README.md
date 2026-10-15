# panel-clock-releases

Gotowe wydania budzika [panel-clock](https://github.com/JacekWalczak92/panel-clock):
APK aplikacji **M5DialPilot** i firmware ESPHome `panel-budzik.yaml`.

Najnowsza wersja: [Releases → Latest](https://github.com/JacekWalczak92/panel-clock-releases/releases/latest).

## Jak powstaje release

Kod źródłowy w panel-clock jest prywatny, dlatego workflow potrzebuje sekretu `SOURCE_TOKEN`:
fine-grained token GitHub z dostępem tylko do repozytorium panel-clock i uprawnieniem
**Contents: Read-only**.


Actions → **Release APK** → Run workflow, w polu `tag` wpisz np. `v14.0.1`
(opcjonalnie `source_ref` = gałąź/commit z panel-clock). Workflow pobiera kod z panel-clock,
buduje APK i publikuje je tutaj razem z YAML-em.

APK jest podpisywane kluczem z sekretów tego repozytorium: `ANDROID_KEYSTORE_BASE64`,
`ANDROID_KEYSTORE_PASSWORD`, `ANDROID_KEY_ALIAS`, `ANDROID_KEY_PASSWORD`.
Bez nich APK dostaje jednorazowy klucz debug i nie zaktualizuje wcześniejszej instalacji.
