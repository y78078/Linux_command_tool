# 7zip

## use 7zip split file

### install
sudo apt-get install p7zip p7zip-full
### command
7z a -mx=9 -tzip -v200m dist_compress_name.zip source_filename

-mx compress ratio

-t(compress type) EX: -tzip -trar -t7z

# package management

## rpm
### rpm2cpio (depress without install)
rpm2cpio your_package.i586.rpm | cpio -div

## dpkg
### dpkg -x your_package.i586.deb new_dir
