# nord-bluish-accent-gtk-theme-snap
nord-bluish-accent-gtk-theme for packaging as a snap

## Updating resources \(Optional -- if upstream has updates\)

\(Icons, both Nordic and Nordzy-curors included for potential future compatibility and may be stripped out in later revision. Right now not aware of any resource that will use them.\)

(This link)[https://www.gnome-look.org/p/1267246/] hosts the theme files \(Not packages for snap\). To update download Nordic-bluish-accent.tar.xz, Nordic-Folders.tar.xz. Unpack these files.
- Replace the Nordic-bluish-accent contents in local-source/share/themes with the contents from Nordic-bluish-accent.tar.xz \(Note: you'll want the nexted folder on the same level as Nordic-bluish-accent-v40, but you can ignore the Nordic-bluish-accent-v40 folder completely).
- Replace the Nordic in local-source/share/icons with the contents from Nordic-Folders.tar.xz \(Note: you can ignore the Nordic-Darker folder completely).

## Creating the snap

### Installing necessary tools
```sh
sudo snap install snapcraft --classic
```

### Building the snap
```sh
snapcraft --destructive-mode
```

## Installing the snap
TODO: Update to strict confinement and stable grade
```sh
sudo snap install nord-bluish-accent-gtk-theme_0.1_all.snap --devmode
```

## Plugging snaps into the theme
```sh
for i in $(snap connections | grep gtk-common-themes:gtk-3-themes | awk '{print $2}'); do sudo snap connect $i nord-bluish-accent-gtk-theme:gtk-3-themes; done
```

