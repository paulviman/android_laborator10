# android_laborator10

Utilizând aplicaţiile anterioare ca sursă de inspiraţie, dezvoltaţi o nouă aplicaţie mobilă care ajustează 
luminozitatea ecranului în funcţie de intensitatea luminoasă a mediului în care se află dispozitivul. Puteţi implementa 
şi un set de controale care să permită ajustarea manuală a luminozităţii ecranului. Pentru rezolvarea acestei teme puteţi 
ţine cont de următoarele aspecte (ce conduc spre una din variantele posibile de rezolvare a temei):
- în general (pentru majoritatea dispozitivelor android testate) luminozitatea ecranului poate fi setată în intervalul de 
valori 0-255 în timp ce valorile furnizare ca ieşire de către senzorul de lumină ambientală sunt cuprinse în intervalul 0-
40000 (în emulatorul Android Studio, verificaţi cazul concret al dispozitivului fizic pe care îl folosiţi).
- verificarea setărilor sistemului se face utilizând: Settings.System.getInt
initialBrightness = Settings.System.getInt(context.getContentResolver(), 
Settings.System.SCREEN_BRIGHTNESS, 0);
- modificarea setărilor sistemului se face utilizând: Settings.System.putInt
Settings.System.putInt(context.getContentResolver(), 
Settings.System.SCREEN_BRIGHTNESS_MODE, Settings.System.SCREEN_BRIGHTNESS_MODE_MANUAL);
Settings.System.putInt(context.getContentResolver(), Settings.System.SCREEN_BRIGHTNESS, 
initialBrightness);
- este necesară acordarea unor permisiuni speciale, notate în fişierul Manifest al aplicaţiei:
<uses-permission android:name="android.permission.WRITE_SETTINGS"
 tools:ignore="ProtectedPermissions" /
