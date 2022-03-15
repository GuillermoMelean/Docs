# <b>Comandos de ajuda react native</b>

## Execute npm package binaries
```sh
npx yarn
```

## Compile project
```sh
npx react-native run-android --variant=BkBrokerDevDebug
```

## Start project
```sh
npx react-native start
``` 

## Start emulator
```sh
emulator -avd Pixel_2_API_30 -writable-system -partition-size 2047 -gpu host
``` 

## Restart android adb service
```sh
adb kill-server && adb start-server
``` 

## Change path 
```sh
cd C:\Users\Guilhermo.Ferreira\Documents\Projetos\PT-SW-SifoxMobile-BK && 
```

## Change path and start project
```sh
cd C:\Users\Guilhermo.Ferreira\Documents\Projetos\PT-SW-SifoxMobile-BK | npx react-native start
``` 

## Clean compilation
```sh
cd android && .\gradlew clean & cd ..
``` 
