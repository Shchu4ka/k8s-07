# Домашнее задание к занятию «Хранение в K8s. Часть 2»

## Задание 1

- Включаем поддержку локального хранения
  ![image](https://github.com/user-attachments/assets/37ae39f6-6e8f-4071-833b-7ca594f049b6)

- Создаем деплой для 2 контейнеров - busybox и multitool и директорию, где будут храниться данные
  ![image](https://github.com/user-attachments/assets/233ebcce-0ece-4231-8284-634c0a243b98)
  ![image](https://github.com/user-attachments/assets/4cc2ef7f-c87f-43fd-b140-4fc8f4d32d26)

- Создаем манифест для PV и PVC
  ![image](https://github.com/user-attachments/assets/f750f140-e1d0-4a1c-a613-8791d3afe044)

- Применяем все манифесты и смотрим, что все ОК
  ![image](https://github.com/user-attachments/assets/9339ea92-1641-4db9-aa9a-ac43c8ed09fb)

- Проверяем, что multitool может читать данные из pvc
  ![image](https://github.com/user-attachments/assets/c93524cf-465a-4735-86af-62714a2253cb)

- Удаляем деплоймент и pvc, видим, что pv перешел в статус released и отвязался от пода
  ![image](https://github.com/user-attachments/assets/fabde9e7-0e63-448d-9f80-527a286e3dcc)

- Видим, что файл сохранился на локальном диске, 
  ![image](https://github.com/user-attachments/assets/bde983f7-8975-4695-ac9c-c6e9f4aacad1)

- Удаляем PV, видим, что файл на месте, так как у PV по умолчанию установлена политика Retain
  ![image](https://github.com/user-attachments/assets/1eab9c97-2a1a-4f82-8095-bd8f4820b884)

## Задание 2

- Ставим и настраиваем NFS-сервер и устанавливаем CSI-драйвер в microk8s
  ![image](https://github.com/user-attachments/assets/03e5f89b-8879-4c59-a1ff-1560e31a701f)

- Создаем деплой для storageclass NFS и применяем его
  ![image](https://github.com/user-attachments/assets/2f07cee1-7059-470b-8b5f-3dd7437cc786)
  ![image](https://github.com/user-attachments/assets/4d41e95a-a89a-462e-a892-308bda73aca7)

- Пишем манифест для PVC и применяем его
  ![image](https://github.com/user-attachments/assets/15b94627-52f8-4df6-a990-86d561517ba0)

- Пишем манифест для деплоя, применяем его
  ![image](https://github.com/user-attachments/assets/fec63134-6f31-477d-9415-8b8b21ad5cb8)
  ![image](https://github.com/user-attachments/assets/6896f90c-ca93-4b44-911f-d5bf95ade2c5)

- Проверяем возможность чтения файла из пода и с локального хоста
  ![image](https://github.com/user-attachments/assets/e591e104-c95f-4172-b85f-e06bf9974708)
