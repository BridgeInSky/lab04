# lab04

```
# Создаем директории для GitHub Actions
mkdir -p .github/workflows
```
Создадим файл travis.yml
```
touch .github/workflows/linux.yml
vim linux.yml
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
Markdown-код для отображения статуса сборки:
![GitHub Actions](https://github.com/<ваш-username>/lab04/workflows/Linux%20Build/badge.svg)
<br>
Коммитим и пушим изменения
```
git add .github/workflows/
git add README.md
git commit -m "Add GitHub Actions workflows for CI"
git push origin main
```
