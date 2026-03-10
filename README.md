Crazy Taxi 3 straight up refuses to recognize any controller that doesn't identify as a steering wheel (DI8DEVTYPE_DRIVING) by not allowing it to map axises. 
vJoy reports itself as a gamepad if you don't teak its Regedit value, and messing with regedit breaks the config you might have for many other games. 
That's why I wanted to create a software/per game solution which resides in this hook.

On top of that, even after faking the device type, CT3 maps its brake and gas to the Y and Z axes in a swapped order compared to what vJoy actually sends, 
so the pedals were backwards. And the last headache: vJoy only outputs half the value range the game expects for pedals, so pressing the gas halfway barely registered on screen, 
and releasing both pedals still showed a tiny bit of braking because the game read the idle value as slightly pressed.

Game expects combined pedals, and haven't been able to force some other config. If you might want to make this dll better, I left a dll "log file" which tells you everything to know to fix it *if you know how to,,, I don't*

This proxy DLL sits between the game and DirectInput8. It spoofs vJoy's device type so CT3 accepts it as a wheel, 
swaps the Y and Z axes so the right pedal does the right thing, and rescales both pedal values from vJoy's half-range to the full range the game actually uses. 

If you wanna reach to me you can come on my portfolio : https://tathan.moe/
or contact me on twitter!

https://x.com/KonoTathan
