![Cosmo](https://github.com/szawel/Kosmogonik/blob/master/img/Kosmo.gif)
# **Ksomogonik / Cosmogonic**
## <b>Spis treści</b>

<a name="nazwy"></a>
## <b>Nazwy Postaci</b>
`Kosmogonik` – Narrator <br />
`Architor` – władca planety <br />
`Pyron` – główny Protagonista <br />
`Palatynidzi | Palatynida | Palatynidów` – mieszkańcy planety <br />

<a name="nazewnictwo"></a>
## <b>Nazewnictwo</b>
<a name="plikiprojektowe"></a>

### Pliki Projektowe
`Nazwa obiektu` + `Rodzaj` + `nr` + `rozszerzenie`<br />
`Kosmogonik` + `_Model` + `_01` + `.blend` <br />
`Kosmogonik_Model_01.blend` <br />

<a name="plikimodelu"></a>
### Pliki Modelu

* Nazwy mają numery jesli jest wiecej niż jeden z tej samej kategotii np. <br/>
`Naczynie_01,` `Naczynie_02,` `Naczynie_02 ` `itd...` <br/>
* Ten numer nie jest tożsamy z numerem wersji który zapisujemy tuż przed rozszerzeniem ! <br />
* W nazwach nie uzywamy `spacji` tylko `_` <br />
* Nazwa zaczyna się z dużej litery raszta małą, tak samo rodzaj ! <br />
* `Low` - oznacza geometrie `LowRes` <br />
* `High` - oznacza geometrie `HighRes` <br />


`Nazwa obiektu` + `Rodzaj` + `Nr` + `Rozszerzenie` <br />
`Kosmogonik` + `Low` + `01` + `.obj` <br />
`Kosmogonik_Low_01.obj` <br />

<i>przykłady:</i>
```
Naczynie_02_High_01.obj
Naczynie_02_Low_01.obj
Naczynie_02_01.obj
...
```

<a name="tekstury"></a>
### Nazewnictwo Tekstury
`Nazwa` + `Nr wersji` + `Suffix` + `Rozszerzenie` <br />
`Kosmogonik` + `_01` + `_AL` + `.png`<br />
`Kosmogonik_01_AL.png`<br />

Suffix | Texture
:------|:-----------------
`_AL`  | Albedo
`_SP`  | Specular
`_R`   | Roughness
`_MT`  | Metallic
`_GL`  | Glossiness
`_N`   | Normal
`_H`   | Height
`_DP`  | Displacement
`_EM`  | Emission
`_AO`  | Ambient Occlusion
`_M`   | Mask

### Asset
Nazewnictwo <br />
`Nazwa Assetu` + `Rodzaj` + `nr` + `rozszerzenie`<br />
Folder <br />
`Kosmogonik_VR\Assets\Postacie\Palatynida_B`
<br />
```c
Palatynida_B        # Nazwa Assetu/Folderu
 +--- geo
 |   +--- Palatynida_B_Low_01.fbx         # fbx Final geometry
 +--- Geo_Bake                            
 |   +--- Palatynida_B_Bake_High.fbx      # fbx HighRes bake
 |   +--- Palatynida_B_Bake_Low.fbx       # fbx LowRes bake
 +--- tex                                 
 |   +--- Palatynida_B_Low_01_AL.png      # Texture Albedo
 |   +--- Palatynida_B_Low_01_MT.png      # Texture Metallic
 |   +--- Palatynida_B_Low_01_N.png       # Texture Normal
 +--- Palatynida_B_Bake_SetUp_01.hiplc    # Houdini File with SetUp
 +--- Palatynida_B_Bake_Tex_01.spp        # Substance Painter SetUp
```

### Nazewnictwo Grupy
```
Kosmogonik            # Nazwa Modelu
+---Kosmogonik_L_Arm  # Kolejno nazwa elemntu
+---Kosmogonik_R_Arm  # w/w
+---...
```
# Struktura Folderów
#### Folder z Projektami

```
H:\Kosmogonik_VR                    
 +---Blender                          # Folder z projektami w Blender
 |   +---Kosmogonik_01                # Folder Projektu
 |   +---+---Kosmogonik_Model_01.blend    
 +---Houdini                          # Folder z projektami w Houdini
 |   +---Kosmogonik_01                # Folder Projektu
 |   +---+---Kosmogonik_Model_01.hip      
 +---Assets
 |   +---Postacie                     # Folder z Assetami
 |   +---+---Kosmogonik_01            # Folder Assetu
 |   +---+---+---Kosmogonik_01.obj    # Plik Assetu
 |   +---+---+---Kosmogonik_01        # Folder Tekstury
 |   +---Rekwizyty
 |   +---Scenografia
 +---Docs
 ```


## FFMPEG
image seq to mp4

```
ffmpeg -i img%04d.png -c:v libx264 -vf fps=25 -pix_fmt yuv420p out.mp4
```
3 video to one side by side
```
ffmpeg.exe -i 01.mp4 -i 02.mp4 -i 03.mp4 -filter_complex "[1:v][0:v]scale2ref=oh*mdar:ih[1v][0v];[2:v][0v]scale2ref=oh*mdar:ih[2v][0v];[0v][1v][2v]hstack=3,scale='2*trunc(iw/2)':'2*trunc(ih/2)'" out.mp4
```

## Houdini env
```
UNITY = "D:/Kosmogonik_Storyboard_VR/Kosmogonik Storyboard VR/Assets/Kosmogonic_Assets"
ASSETS = "D:/Kosmogonik_VR/Assets"
HOUDINI_PATH = "$UNITY;$ASSETS;&"
```
