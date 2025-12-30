= Install

== Freedesktop
=== Extend desktop paths
Create sudo nano /etc/profile.d/xdg_paths.sh
put this in,
export XDG_DATA_DIRS="$XDG_DATA_DIRS:/home/rob/.local/share"

restart computer
check registered,
printenv XDG_DATA_DIRS


=== Set MIME
mkdir -p ~/.local/share/mime/packages
copy tml.xml to
~/.local/share/mime/packages

update-mime-database -V ~/.local/share/mime/

Check mime registered,
cat ~/.local/share/mime/types



== GtkSourceview
=== Add definition
Copy tml.lang to
mkdir -p ~/.local/share/gtksourceview-3.0/language-specs/

Shutdown all text editors and restart


== Set Icon
NB: Only for my setup. Paths will need adjusting for other themes.

sudo mkdir /usr/share/icons/Mint-Y/mimetypes/scalable
sudo nano /usr/share/icons/Mint-Y/index.theme

In nano add,
Directories=mimetypes/scalable,...

##### custom

[mimetypes/scalable]
Size=16
Context=Mimetypes
Type=Scalable
MinSize=8
MaxSize=512

######

sudo gtk-update-icon-cache path/to/the/theme/folder


== Geany
{em NEVER WORKED}

cppy to /home/rob/.config/geany/filedefs
filetypes.TML.conf

=== Change config
In /home/rob/.config/geany/filetype_extensions.conf
or,
In geany itself, ''Tools > Configuraation Files > filetype_extensions.conf'

Uner [Extensions] add,
#- TML=*.tml;
Under [Groups] append to this line (line usually empty)
#~ Markup=TML;
