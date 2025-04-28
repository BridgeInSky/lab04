# lab04
[![Build Status](https://app.travis-ci.com/BridgeInSky/lab04.svg?token=TETaThcBJdejLLYy99ah&branch=main)](https://app.travis-ci.com/BridgeInSky/lab04)
Клонируем репозиторий:
```
git clone https://github.com/BridgeInSky/lab04.git
cd lab04
```
Создадим файл travis.yml
```
vim .travis.yml
```
Содержимое файла:
```
language: cpp

os: linux  # Сборка на Linux

compiler:
  - gcc    # Тест с GCC
  - clang  # Тест с Clang

before_install:
  - sudo apt-get update -qq
  - sudo apt-get install -y cmake

script:
  - mkdir build && cd build
  - cmake ..
  - cmake --build .
```
Запушим изменения:
```
git add .travis.yml
git commit -m "Add TravisCI configuration"
git push origin main
```
