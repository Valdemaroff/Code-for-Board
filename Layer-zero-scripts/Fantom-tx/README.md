Данный скрипт рассылает дешевые транзакции с одного кошелька, сид которого прописываем в скрипте.

## Гайд
```
sudo apt update && sudo apt upgrade -y
git clone https://github.com/Valdemaroff/Code-for-Board/tree/main/Layer-zero-scripts/Fantom-tx
cd /root/Fantom-tx
apt install python3-pip
pip install tqdm ccxt loguru termcolor telebot pyuseragents tabulate web3 pandas
```
После установки нам надо отредактировать файл [main.py](https://github.com/Valdemaroff/Code-for-Board/blob/main/Layer-zero-scripts/Fantom-tx/main.py)
#### Вставить private_key
Скрипт отрабатывает только по одному кошельку. Для этого замените `PRIVATE_KEY` на ключь от нужного вам кошелька.
- 4 строка
```
private_key = "PRIVATE_KEY"
```
 В консоль вписать сколько нужно прогнать транз.

 #### Запуск
```bash
# Заходим в папку скрипта
cd /root/Fantom-tx

# Запуск с выводом stdout в командную строку
python3 main.py
# Запуск в фоновом режиме. Записывает логи в файл log.log
nohup python3 main.py > log.log 2>&1 &

# Завершить процесс:
pgrep -a python
kill (номер процесса)
```
