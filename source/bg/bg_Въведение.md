Въведение
=========

**Какво е AndroidAPS ?**

Основни цели при създаването на това приложение
-----------------------------------------------

* модулно приложение с възможност лесно да се добавят нови модули, без да се променя останалата част от кода
* приложение, което позволява локализация на различни езици
* приложение, където можем лесно да изберем това, което ще бъде включено в окончателния apk файл чрез промяна на варианта на компилацията
* приложение, което поддържа отворен и затворен режим на APS
* приложение, където можете да видите как работи APS: параметри на входа, резултати и окончателно решение
* позволява да се добавят още алгоритми за APS, като потребителя има възможност да избира кой от тях да използва
* приложение, независимо от драйвера на помпата, съдържащо и "Виртуална помпа", което позволява на потребителите безопасно да изпробват APS
* приложение с плътна интеграция с Nightscout
* приложение, където е възможно лесно да се добавят / премахват ограничения за безопасността на потребителите
* приложение "всичко в едно" за управление на Диабет с APS и Nightscout

Какво е нужно за да започнете
-----------------------------

* Android телефон (5.0 или по-нова версия)
  * [xDrip](http://stephenblackwasalreadytaken.github.io/xDrip/)/[xDrip+](https://github.com/jamorham/xDrip-plus) или [Glimp](http://www.nightscout.info/wiki/welcome/nightscout-for-libre) или [600SeriesAndroidUploader](https://github.com/pazaan/600SeriesAndroidUploader)
  * [AndroidAPS](https://github.com/MilosKozak/AndroidAPS)
* [Nightscout](https://github.com/nightscout/cgm-remote-monitor) 0.10.2 или по-нова
* Инсулинова помпа Dana-R (освен ако не създадете свой собствен драйвер за друга инсулинова помпа)
* Източник на данни за непрекъснат мониторинг на кръвната захар (CGM)
  * Dexcom G4/G5 или Freestyle Libre или Medtronic Guardian
  
Безопасност
===========
  
** Когато решите да изградите свой собствен Closed Loop (затворен режим) винаги мислете за сигурността и последиците от всяко ваше действие **

Обща безопасност
----------------

* AndroidAPS е просто инструмент, който да ви помага да управлявате диабета. Не е нещо, което можете да инсталирате и да забравите за него!
* Не се доверявайте изцяло на всяко устройство, което контролира доставянето на инсулин. Наблюдавайте го през цялото време, научете как работи и научете как може да предвидите резултата от него.
* Запомнете, че телефон свързан с помпата, може да направи всичко с вашата помпа. Използвате телефон само за APS и комуникация с детето си. Не позволявайте инсталиране на други приложения и игри (!!!), за да предотвратите инсталирането на някои нежелани приложения като троянски коне, вируси или ботове.
* Инсталирайте всички актуализации на защитата, предоставени от телефонния производител и Google.

SMS комуникатор
---------------

* Ако активирате SMS Communicator, помислете какво може да се случи, когато телефонът, активиран за отдалечени команди, е откраднат! Винаги го пазете, защитете го поне с PIN код
* След AndoridAPS 1.1 вие ще получавате SMS известяване за важни дистанционни действия като болус или промяна на профила. Настройте най-малко 2 номера за SMS комуникация, за да бъдете уведомявани за действията на втория телефонен номер (в случай, че първият е откраднат и от него се изпращат SMS команди)

Скрийншоти
==========

![Overview](https://img1.picload.org/image/dgdgcorw/aaps-overview-small.jpg.png)
![Actions](https://img1.picload.org/image/dgdgcoar/aaps-actions-small.png)
![Pump](https://img1.picload.org/image/dgdgcooa/aaps-pump-small.jpg)
![Careportal](https://img1.picload.org/image/dgdgcoow/aaps-careportal-small.jpg)
![Loop](https://img1.picload.org/image/dgdgcioi/aaps-loop-small.jpg)
![OpenAPSAMA](https://img1.picload.org/image/dgdgcocw/aaps-openapsma-small.jpg)
![NS-Profile](https://img1.picload.org/image/dgdgcoir/aaps-ns-profile-small.jpg)
![Objectives](https://img1.picload.org/image/dgdgciol/aaps-objectives-small.jpg)
![Treatments](https://img1.picload.org/image/dgdgciow/aaps-behandlungen-small.jpg)
![ConfigBuilder1](https://img1.picload.org/image/dgdgcilr/aaps-config-builder-small.jpg)
![ConfigBuilder2](https://img1.picload.org/image/dgdgcila/aaps-config-builder2-small.jpg)

Архитектура,-security-implementation
====================================

Програмата се състои от различни плъгини. Всеки от тях трябва да притежава(extends) Fragment, да имплементира(implements) PluginBase, а също може да имплементира някой от интерфейсите(Interfaces). Примерна декларация на плъгин би изглеждала така: 

`public class ConfigBuilderFragment extends Fragment implements PluginBase, PumpInterface, ConstraintsInterface`

Всеки плъгин трябва да бъде разработен като самостоятелен код. Единствената редакция, която е необходима за интегрирането му с останалата част от програмата е в клас `MainActivity` и изглежда така:

`pluginsList.add(SourceXdripFragment.newInstance());`

Когато плъгина, който разработваме, трябва да се свърже с други плъгини, то това винаги трябва да става чрез клас `ConfigBuilder`. Например за да изпратим команда към помпата: 

```
PumpInterface pump = MainApp.getConfigBuilder().getActivePump();
PumpEnactResult result = pump.deliverTreatment(insulin, carbs);
```

![App design](../images/app_desing.png)

Самият `ConfigBuilder` е един вид интерфейс за помпата(`PumpInterface`) и интерфейс за ограниченията(`ConstraintInterface`). Така чрез извикване на функцията `MainApp.getConfigBuilder().getActivePump()` `ConfigBuilder` ще върне себе си като резултат. Така като изпращате команда към помпата `ConfigBuilder` първо проверява за спазване на ограниченията и тогава изпраща същинската команда към драйвера на помпата.

Това позволява добавянето на специфични ограничения към програмата, без необходимост от промяна на останалия код. Например чрез създаването и регистрирането на този Fragment:

```
public class BolusConstraint extends Fragment implements PluginBase, ConstraintsInterface {
    @Override
    public boolean isLoopEnabled() {
        return true; // Always enable, limit only things you want
    }

    @Override
    public boolean isClosedModeEnabled() {
        return true; // Always enable, limit only things you want
    }

    @Override
    public boolean isAutosensModeEnabled() {
        return true; // Always enable, limit only things you want
    }

    @Override
    public boolean isAMAModeEnabled() {
        return true; // Always enable, limit only things you want
    }

    @Override
    public APSResult applyBasalConstraints(APSResult request) {
        return request; // Don't change, limit only things you want
    }

    @Override
    public Double applyBasalConstraints(Double absoluteRate) {
        return absoluteRate; // Don't change, limit only things you want
    }

    @Override
    public Integer applyBasalConstraints(Integer percentRate) {
        return percentRate; // Don't change, limit only things you want
    }

    @Override
    public Double applyBolusConstraints(Double insulin) {
        if (insulin > 2d) insulin = 2d;
        return insulin;
    }

    @Override
    public Integer applyCarbsConstraints(Integer carbs) {
        return carbs; // Don't change, limit only things you want
    }

    @Override
    public Double applyMaxIOBConstraints(Double maxIob) {
        return maxIob; // Don't change, limit only things you want
    }

    @Override
    public int getType() {
        return PluginBase.CONSTRAINTS;
    }

    @Override
    public String getName() {
        return "Bolus Constraint";
    }

    @Override
    public boolean isEnabled() {
        return true; // Always enabled and cannot be disabled
    }

    @Override
    public boolean isVisibleInTabs() {
        return false; // No need to have own tab in GUI
    }

    @Override
    public boolean canBeHidden() {
        return true;
    }

    @Override
    public void setFragmentEnabled(boolean fragmentEnabled) {
        // Do nothing, always enabled
    }

    @Override
    public void setFragmentVisible(boolean fragmentVisible) {
        // Do nothing, always hidden
    }
}
```
Ние ограничаваме размера на болус до 2 единици навсякъде в програмата.

`ConfigBuilder` винаги преминава през всички регистрирани интерфейси на ограничения ('ConstraintInterfaces') и избира най-ограничената стойност, преди да я предаде към  избрания драйвер на помпа.

Добавянето на драйвер на помпа може да включи интерфейса за ограниченията(ConstraintInterface) също, да зареди максималните стойности от помпата и да ги приложи като допълнително ограничение. Тогава например графичният интерфейс няма да позволи въвеждането на по-голям болус.


Терминология
============

????????????????
