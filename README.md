# **Ksomogonik**
## Spis treści
1. [ Description. ](#desc)
2. [ Usage tips. ](#usage)

# Nazwy
`Kosmogonik` – Narrator <br />
`Architor` – władca planety <br />
`Pyron` – główny Protagonista <br />
`Palatynidzi | Palatynida | Palatynidów` – mieszkańcy planety <br />

<a name="desc"></a>
# <b>Nazewnictwo<b>
### Pliki Projektowe
`Nazwa obiektu` + `Rodzaj` + `nr` + `rozszerzenie`<br />
`Kosmogonik` + `_Model` + `_01` + `.blend` <br />
`Kosmogonik_Model_01.blend` <br />

### Pliki Modelu
`Nazwa obiektu` + `Nr` + `Rozszerzenie` <br />
`Kosmogonik` + `_01` + `.obj` <br />
`Kosmogonik_01.obj` <br />

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


### Development Postacie

`Kosmogonik_VR\Development\Palatynidzi_01`
<br />
```
Palatynidzi_01               # Folder
 |  Palatynidzi_01.hiplc
 |  Palatynidzi_01.zpr
 |  +--- geo                               # geometria .obj albo .fbx itp
 |  +--- export                            # tylko czysty export
 |  +---+--- Palatynida_A_Base_01.obj      # mockap postaciw w T-Pose
 |  +---+--- Palatynida_A_Low_01.obj       # optymalizacja Midle
 |  +---+--- Palatynida_A_Midle_01.obj     # export z Zbrush
 |  +---+--- Palatynida_A_High_01.obj      # export z Zbrush
 |  +--- tex
 |  +---+--- Palatynida_A_01_N.png         
 |  +---+--- Palatynida_A_01_AO.png
```

### Asset
```
Nazwa               # Folder
 |  +---Model       # geometria .obj albo .fbx
 |  +---Shader      # *.meta tylko do Unity
 |  +---+---Texture # Folder z setem tekstur
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
