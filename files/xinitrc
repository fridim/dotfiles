#!/bin/sh
#
# ~/.xinitrc
export LC_TIME=en_DK.UTF-8
export GOPATH=/home/fridim/.go

# allow per-machine xinitrc
[ -e ~/.xinitrc.local ] && . ~/.xinitrc.local

if [ -d /etc/X11/xinit/xinitrc.d ]; then
  for f in /etc/X11/xinit/xinitrc.d/*; do
    [ -x "$f" ] && . "$f"
  done
  unset f
fi

eval $(gpg-agent --daemon --default-cache-ttl 600 --enable-ssh-support --write-env-file "${HOME}/.gpg-agent-info")

for runf in /home/fridim/sync/bin/my_xrandr; do
    [ -e "${runf}" ] && ${runf}
done

# background
feh --bg-center /home/fridim/wallpapers/archlinux/purple-1920x1080.png

#pidgin&   # use now bitlbee \o/
#claws-mail&
dunst -conf ~/.dunstrc &
#chromium&
firefox&  # Vimperator++
#thunderbird&
#korganizer&
#zim&
#xscreensaver&
redshift -l 43.5394:3.6917 -t 5700:3600 &
setxkbmap -option compose:ralt

# remove Beep!
xset b off &

synclient TouchpadOff=1

#synergys -d FATAL

# DANGEROUS IF YOU COPY/paste passwords
#clipit&

#choqok&
#mumble&
#ekiga&   # not working with my usb headset
#jitsi&

#exec awesome
#exec enlightenment_start
#exec clfswm
#exec dwm
#exec gnome-session
#exec startkde
#exec startxfce4
#exec xmonad
#exec subtle
#exec /home/fridim/apps/stumpwm/stumpwm
/usr/lib/polkit-gnome/polkit-gnome-authentication-agent-1 &

# screenshoting
flameshot&

exec i3
