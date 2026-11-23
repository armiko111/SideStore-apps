# Как установить SideStore на iPhone с компьютера Windows

Вам понадобятся компьютер с Windows, USB-кабель с поддержкой передачи данных, iPhone с код-паролем, Wi-Fi и бесплатный Аккаунт Apple. Используйте свой Аккаунт Apple и в iLoader, и в SideStore. Компьютер и кабель нужны для первой установки и для восстановления сопряжения, если оно перестанет работать.

> **Перед каждым действием в SideStore подключайте iPhone к Wi-Fi и включайте LocalDevVPN.** Оставляйте оба подключения активными, пока меняете настройки SideStore, входите в аккаунт, добавляете источник, устанавливаете или обновляете приложения и продлеваете срок действия подписей.

## 1. Включите режим разработчика на iPhone

1. На iPhone откройте **Настройки → Конфиденциальность и безопасность → Режим разработчика** (**Settings → Privacy & Security → Developer Mode**).
2. Включите **Режим разработчика** и нажмите **Перезагрузить** (**Restart**). После перезагрузки разблокируйте iPhone, нажмите **Включить** (**Turn On**) и введите код-пароль.
3. Если пункта **Режим разработчика** нет, выполните шаги 2 и 3, затем вернитесь сюда. Пункт может появиться после сопряжения с компьютером или установки SideStore. Режим разработчика доступен начиная с iOS 16. [Инструкция Apple по режиму разработчика](https://developer.apple.com/documentation/xcode/enabling-developer-mode-on-a-device)

## 2. Установите Apple Devices на Windows

1. Откройте Microsoft Store и установите **Apple Devices** от Apple Inc. В русской версии магазина приложение может называться **Устройства Apple**. [Скачать Apple Devices](https://apps.microsoft.com/detail/9np83lwlpz9k)
2. Подключите разблокированный iPhone по USB. Откройте **Apple Devices**, выберите iPhone в боковой панели и нажмите **Доверять** (**Trust**), если запрос появится на компьютере или iPhone. При необходимости введите код-пароль iPhone.
3. Убедитесь, что iPhone появился в Apple Devices. Если его нет, разблокируйте телефон, подключите его заново кабелем с поддержкой передачи данных или попробуйте другой USB-порт. Если Apple Devices видит iPhone, а iLoader его не видит, попробуйте установить драйверы через iTunes по [инструкции SideStore для Windows](https://docs.sidestore.io/docs/installation/prerequisites).

## 3. Установите последнюю версию SideStore через iLoader

1. На компьютере откройте страницу последнего релиза **iLoader**. В разделе **Assets** скачайте и запустите MSI для Windows. Для большинства компьютеров подойдёт `iloader-windows-x64.msi`. [Релизы iLoader](https://github.com/nab138/iloader/releases/latest)
2. Оставьте iPhone подключённым и разблокированным. Откройте iLoader, выберите iPhone и войдите в свой бесплатный Аккаунт Apple. Если Apple запросит код подтверждения, введите его.
3. Нажмите **Install SideStore (Stable)**, если там доступна актуальная версия. Если кнопка устанавливает версию **0.6.4 или старше** либо вы хотите выбрать последнюю опубликованную сборку вручную, скачайте **SideStore.ipa** из раздела **Assets** на официальной странице релиза. В iLoader нажмите **Install IPA** и выберите файл. На момент проверки инструкции последним опубликованным релизом был **0.7.0-alpha**. В примечаниях к релизу указано, что в версии 0.6.4 и более ранних есть проблемы со входом. [Релизы SideStore](https://github.com/SideStore/SideStore/releases/latest) · [Инструкция по установке через iLoader](https://docs.sidestore.io/docs/installation/install)
4. Когда появится значок SideStore, откройте на iPhone **Настройки → Основные → VPN и управление устройством → Приложение разработчика → ваш Аккаунт Apple → Доверять** (**Settings → General → VPN & Device Management → Developer App → your Apple Account → Trust**). Если появится кнопка **Allow & Restart** («Разрешить и перезагрузить»), нажмите её и следуйте указаниям на экране. Если раньше пункта **Режим разработчика** не было, включите его по шагу 1.
5. Перед первым запуском SideStore выполните шаг 5. Обычно iLoader сам помещает файл сопряжения в SideStore при установке.

## 4. Восстановите или импортируйте файл сопряжения при необходимости

Пропустите этот раздел, если SideStore открывается без запроса файла сопряжения и успешно продлевает срок действия подписей. Для каждого iPhone нужен свой файл сопряжения. Храните его в закрытом доступе. После обновления или сброса iOS может понадобиться новый файл.

**Сначала попробуйте iLoader.** Подключите разблокированный iPhone. Выберите его в iLoader, нажмите **Delete Stored Pairing**, затем снова выберите iPhone и подтвердите **Доверять** (**Trust**) на телефоне. Откройте **Manage Pairing File** и нажмите **Place** рядом с **SideStore**. [Инструкция SideStore по восстановлению сопряжения](https://docs.sidestore.io/docs/advanced/pairing-file)

**Если нужно создать файл вручную, используйте idevice_pair.**

1. На компьютере скачайте файл для Windows из раздела **Assets** и запустите его. Оставьте iPhone подключённым и разблокированным. [Релизы idevice_pair](https://github.com/jkcoxson/idevice_pair/releases/latest)
2. Выберите iPhone в idevice_pair. В разделе **Pairing file** выберите **Lockdown**, затем нажмите **Create** или **Load**, в зависимости от того, какая кнопка появится. Если iPhone запросит разрешение, нажмите **Доверять** (**Trust**).
3. В разделе **Send to an app** нажмите **SideStore** и дождитесь надписи **Sent**. Если хотите выбрать файл вручную, нажмите **Save to file…** и сохраните исходное расширение `.mobiledevicepairing` или `.plist`. Перенесите файл в приложение **Файлы** на iPhone, например через свой iCloud Drive.
4. Подключите **LocalDevVPN** и Wi-Fi. Если при запуске SideStore попросит файл сопряжения, выберите его в приложении **Файлы**. Чтобы заменить файл из самого SideStore, откройте **Settings → Advanced Settings → Reset Pairing File** и следуйте указаниям на экране выбора файла. [Кнопки idevice_pair](https://github.com/jkcoxson/idevice_pair/blob/v1.2.0/src/ui/device_page.rs) · [Форматы файлов сопряжения SideStore](https://github.com/SideStore/SideStore/blob/0.7.0-alpha/SideStore/Core/Pairing/PairingFileManager.swift)

## 5. Установите и подключите LocalDevVPN

1. На iPhone установите **LocalDevVPN** из App Store. [Скачать LocalDevVPN](https://apps.apple.com/app/localdevvpn/id6755608044)
2. Подключите iPhone к **Wi-Fi**. Откройте **LocalDevVPN** и нажмите **Connect**. Если iOS запросит разрешение на добавление конфигурации VPN, нажмите **Разрешить** (**Allow**) и введите код-пароль.
3. Убедитесь, что LocalDevVPN показывает **Connected**. Оставляйте VPN включённым при каждом действии в SideStore, в том числе при изменении настроек и добавлении источника. Когда SideStore и файл сопряжения установлены, iPhone можно отключить от компьютера. [Сетевые требования SideStore](https://docs.sidestore.io/docs/installation/prerequisites)

## 6. Настройте SideStore и войдите в аккаунт

Используйте значения из файла `SideStoreConfig.txt`. Меняйте настройки внутри **SideStore** при активных подключениях **LocalDevVPN и Wi-Fi**.

1. В SideStore нажмите **Settings** (значок шестерёнки) и откройте **Advanced Settings → User Customizations**. В разделе **Anisette** выключите **On-Device Anisette**. Если приложение попросит перезапустить его, закройте и снова откройте SideStore. Убедитесь, что LocalDevVPN всё ещё подключён.
2. Вернитесь на главный экран **SideStore → Settings** и откройте **Anisette Servers**. Выберите сервер **jkcoxson**. Прокрутите этот же экран вниз и выключите **Enable Auto Rotation**.
3. Откройте **SideStore → Settings → Advanced Settings → User Customizations → Anisette Client Configuration**. Замените содержимое поля **Client Info** этой строкой.

   ```text
   <MacBookPro13,3> <Mac OS X;26.6;25F84> <com.apple.AuthKit/1 (com.apple.akd/1.0)>
   ```

4. На том же экране замените содержимое поля **User Agent** этой строкой.

   ```text
   akd/1.0 CFNetwork/811.5.4 Darwin/16.7.0
   ```

5. Нажмите **Save Overrides**. Снова откройте **Anisette Client Configuration** и проверьте, что оба значения сохранились. Вставляйте в каждое поле только строку из блока кода, без имён полей JSON и кавычек. [Обсуждение настроек и ошибки входа SideStore](https://github.com/SideStore/SideStore/issues/1744)
6. Вернитесь в **SideStore → Settings → Sign in with Apple ID**. Войдите в тот же Аккаунт Apple, который использовали в iLoader. Если потребуется, подтвердите вход с помощью двухфакторной аутентификации.
7. Перед добавлением приложений откройте **SideStore → My Apps** и нажмите на счётчик оставшихся дней рядом с **SideStore**, чтобы продлить подпись самого SideStore. Если появится запрос на завершение первого обновления подписи, подтвердите его. Дождитесь завершения. [Инструкция SideStore по первому продлению подписи](https://docs.sidestore.io/docs/installation/install)

## 7. Добавьте источник armcracka Apps и установите приложение

1. Чтобы получить ссылку на источник, откройте на GitHub **armiko111/SideStore-apps → source.json**, нажмите **Raw** и скопируйте адрес. Домен в ссылке должен быть `raw.githubusercontent.com`. [Открыть source.json на GitHub](https://github.com/armiko111/SideStore-apps/blob/main/source.json)
2. Ту же ссылку можно скопировать здесь.

   ```text
   https://raw.githubusercontent.com/armiko111/SideStore-apps/main/source.json
   ```

3. Подключите **LocalDevVPN** и **Wi-Fi**, затем откройте **SideStore → Sources → +**. Если в вашей версии пункт **Sources** находится во вкладке **Browse**, откройте его оттуда. Вставьте ссылку на исходный файл JSON и подтвердите добавление кнопкой **Add** или **✓**. В списке источников должен появиться **armcracka Apps**. [Документация SideStore об источниках](https://docs.sidestore.io/docs/advanced/app-sources)
4. Откройте источник, выберите **armcracka LangLearn** и нажмите **FREE** или **Install**. После установки откройте приложение с экрана «Домой». На момент написания инструкции LangLearn доступен в этом источнике.
5. Чтобы установить скачанный IPA напрямую, сохраните его в приложении **Файлы** и откройте **SideStore → My Apps → +**. Выберите IPA при активных подключениях **LocalDevVPN и Wi-Fi**.

## Продление подписей и устранение ошибок

- **До истечения семи дней** подключите **Wi-Fi** и **LocalDevVPN**, откройте **SideStore → My Apps → Refresh All** и дождитесь, пока счётчики оставшихся дней обновятся. Бесплатный Аккаунт Apple обычно позволяет держать активными три приложения, установленные таким способом, включая SideStore. [Частые вопросы о SideStore](https://docs.sidestore.io/docs/faq.html)
- **Ошибка сопряжения или код 1414.** Сначала проверьте Wi-Fi и LocalDevVPN. Если оба подключения активны, попробуйте восстановить файл сопряжения по шагу 4. [Коды ошибок SideStore](https://docs.sidestore.io/docs/troubleshooting/error-codes)
- **При входе по-прежнему появляется HTTP 503.** Проверьте, что оба значения заголовков сохранены, выбран сервер **jkcoxson** и автоматическое переключение серверов выключено. Если это не помогло, проверьте актуальные решения в [обсуждении ошибки входа](https://github.com/SideStore/SideStore/issues/1761).
- **Источник не загружается.** Откройте исходную ссылку в Safari. По ней должен отображаться JSON. Если файл не открывается или содержит ошибки JSON, владельцу источника нужно исправить его на GitHub.
