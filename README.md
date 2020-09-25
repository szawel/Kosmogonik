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
