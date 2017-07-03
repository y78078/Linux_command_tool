#use 7zip split file

## install
sudo apt-get install p7zip p7zip-full
## command
7z a -mx=9 -tzip -v200m file.iso ~/dist_filename
-mx compress ratio
-t(compress type) EX: -tzip -trar -t7z
