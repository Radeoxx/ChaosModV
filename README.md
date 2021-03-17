# Chaos Mod V

Una réplica de los chaos mods que se encuentran en juegos de GTA anteriores para GTA V.

Visita la [página del mod [GTA5-Mods]](https://www.gta5-mods.com/scripts/chaos-mod-v-beta) para obtener más información e instrucciones sobre cómo instalarlo.

Siéntase libre de unirse al servidor de Discord para obtener soporte de la comunidad o simplemente para mantenerse actualizado sobre este (y otros) mods.

También asegúrese de comprobar la [Wiki en español](https://github.com/Radeoxx/ChaosModV/wiki) o la [Wiki original](https://github.com/gta-chaos-mod/ChaosModV/wiki)!

[![](https://discord.com/api/guilds/785656433529716757/widget.png)](https://discord.gg/w2tDeKVaF9)

## Compilacion

1. Clonar el repositorio `git clone https://github.com/gta-chaos-mod/ChaosModV.git`

2. `cd ChaosModV`

3. Inicializar todos los submódulos

```
git submodule init
git submodule update --recursive
```

4. Abrir `vendor/minhook/build/VC15/MinHookVC15.sln` en Visual Studio

5. Compile libMinHook como Release x64

6. Abra `ChaosMod.sln` en la carpeta raíz con Visual Studio

7. La compilación debería funcionar ahora. Si hay un error al hacer referencia a `MsBuildMajorVersion` al compilar los proyectos ConfigApp o TwitchChatProxy, cierre y abra Visual Studio nuevamente.

## Añadiendo nuevos efectos

1. Agregue su nueva información de efecto a `ChaosMod/Effects/EffectsInfo.h`

2. Agregue la misma información a `ConfigApp/Effects.cs`

3. Cree un nuevo archivo .cpp en la carpeta apropiada bajo `ChaosMod/Effects/db/` con un nombre apropiado

El diseño del archivo debería ser así:

```cpp
/*
	Effect by <Tu Nombre>
*/

#include <stdafx.h>

static void OnStart()
{
	
}

static void OnStop()
{
	
}

static void OnTick()
{
	
}

static RegisterEffect registerEffect(EFFECT_ENUM_ENTRY, OnStart, OnStop, OnTick);
```

Cualquiera de estas funciones puede omitirse y reemplazarse con un "nullptr" o dejarse completamente fuera (valores de parámetro predeterminados) en la declaración "RegisterEffect".
