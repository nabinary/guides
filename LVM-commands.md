<!-- by nabinary -->
# LVM.  Основные команды
`<param>` - обязательный параметр  
`[param]` - опциональный параметр

| **Physical Volume**<br>**PV**       | ㅤㅤㅤ  **Volume Group**<br>**VG**       |  ㅤㅤㅤ **Logical Volume**<br>**LV**       |
| -------- | -------- | -------- |
| `pvcreate <device>` - создание PV | `vgcreate <vg-name> <device>` - создание VG | `lvcreate -L <size> -n <lv-name> <vg>` - создание LV |
| `pvremove <device>` - удаление PV | `vgremove <vg-name>` - удаление vg | `lvremove <lv-name>` - удаление LV |
| `pvdisplay [device]` - отобразить PV | `vgdisplay [vg-name]` - отобразить vg | `lvdisplay [lv-name]` - отобразить LV |
| `pvs` - компактное отображение всех PV | `vgs` - компактное отображение всех VG | `lvs` - компактное отображение всех LV|
| | `vgextend <vg-name> <pv>` - добавить PV к VG | `lvextend <options>` - расширение LV |

## **lvextend**
### Параметры (это далеко не все):
`-l` - размер в логических экстентах или процентах  
`-L` - размер в абсолютных единицах *(KB, MB, GB...)*  
`-r` - расширение файловой системы вместе с расширением пространства LV  
`--forse` - игнорировать предупреждения


### Сценарии
`lvextend -L +10G <путь до LV>` - расширение пространства LV на 10 GB  
`lvextend -l +50%FREE <путь до LV>` - расширение пространства LV на 50% от свободного места в VG