

## install /setup 


On a linux ubuntu-like system

    sudo apt install -y mesa-utils libgl1-mesa-dri
    git clone git@github.com:two-frontiers-project/cuvette_holder.git
    cd cuvette_holder

    cd ~/bin
    wget https://github.com/FreeCAD/FreeCAD/releases/download/0.21.2/FreeCAD-0.21.2-Linux-x86_64.AppImage
    chmod +x FreeCAD-0.21.2-Linux-x86_64.AppImage
    cd -

Paths needed to get to work on a popOS system, YMMV

    QT_XCB_FORCE_SOFTWARE_OPENGL=1
    export QT_XCB_FORCE_SOFTWARE_OPENGL
    LD_PRELOAD=/usr/lib/x86_64-linux-gnu/libdrm_amdgpu.so.1
    export LD_PRELOAD

Run

    ~/bin/FreeCAD-0.21.2-Linux-x86_64.AppImage

## Modifications

open `cuvette_holder/variants/3d_print/flanged/cuvette_holder.FCStd`

In spreadsheet, modify these measures:

    CuvetteLength = CuvetteWidth = 13.5 mm
    CuvetteCapDiameter = 24.5 mm
    BaseUpperMargin = 10 mm

    # this reduces the upper part of holder 10mm
    CuvetteHeight = 45 mm - 12.5 mm

save as `cuvette_holder_2FPcultureTubeGlassChevron.FCStd`

## export stl

    1) open saved file `cuvette_holder_2FPcultureTubeGlassChevron.FCStd`
    2) mesh in menu selector
    3) select `Body`
    4) Go to 'Meshes' -> 'Create mesh from shape ...' 
    5) Select the 'Standard' meshing option set the 'surface deviation' to 0.001 mm and the 'Angular deviation' to 1 degree.
    6) OK
    7) right click on the mesh in the 'Model' tab of the combo view and select 'Export Mesh ...' 

Save as `cuvette_holder_2FPcultureTubeGlassChevron.stl`
