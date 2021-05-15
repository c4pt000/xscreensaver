# changes to xscreensaver "SBall" screensaver -> "Atomic" added PAM support +RPMS +DEBS for fprintd **WIP (buggy fingerprint)

# requires https://github.com/c4pt000/Validity-sensors-fprint-demo-fingerprint-gui-biometric-fedora

* fedora 34

```

yum install  perl pkg-config gettext intltool lsb -y
yum install gettext pam-devel gtk2-devel desktop-file-utils systemd-devel libcap-devel xorg-x11-proto-devel -y

./configure --prefix=/usr --with-pam --with-pam-service-name --enable-pam-account --with-kerberos --with-shadow
make -j24
make -j24 install
checkinstall --install=no              "deb"
alien --scripts --to-rpm xscreen*.deb
```

place pam.d-xscreensaver.txt in /etc/pam.d/xscreensaver
place 45-fingerprint.rules in /etc/udev/rules.d

per your fingerprint device:vendor

cat /etc/udev/rules.d/100-Validity_FingerPrint_Sensor.rules 
```
SUBSYSTEM=="usb",ATTR{idVendor}=="138a",ACTION=="add",RUN+="/usr/sbin/UsbPlugged"
SUBSYSTEM=="usb",ACTION=="remove",RUN+="/usr/sbin/UsbPlugged"
SUBSYSTEM=="usb",ACTION=="remove",RUN+="/usr/bin/test.sh"
```



cat /etc/pam.d/sudo
```
#%PAM-1.0


auth		sufficient  	pam_fprint.so
auth		sufficient  	pam_fprintd.so


auth       include      system-auth
account    include      system-auth
password   include      system-auth
session    optional     pam_keyinit.so revoke
session    required     pam_limits.so
session    include      system-auth
```

cat /etc/pam.d/system-auth
# dont use fprint here or risk getting locked out of lightdm, gdm
* use with caution can lock lightdm or gdm unless another tty is opened with crtl-alt-F2->F5

```
# Modified system-auth for multi-factor authentication


#auth            sufficient      pam_fprint.so
#auth            sufficient      pam_fprintd.so


session    required     pam_limits.so

auth        required                                     pam_env.so
auth        required                                     pam_faildelay.so delay=2000000
auth        [default=1 ignore=ignore success=ok]         pam_usertype.so isregular
auth        [default=1 ignore=ignore success=ok]         pam_localuser.so
auth        sufficient                                   pam_unix.so nullok try_first_pass
auth        [default=1 ignore=ignore success=ok]         pam_usertype.so isregular
auth        sufficient                                   pam_sss.so forward_pass
auth        required                                     pam_deny.so

account     required                                     pam_unix.so
account     sufficient                                   pam_localuser.so
account     sufficient                                   pam_usertype.so issystem
account     [default=bad success=ok user_unknown=ignore] pam_sss.so
account     required                                     pam_permit.so

password    requisite                                    pam_pwquality.so try_first_pass local_users_only
password    sufficient                                   pam_unix.so sha512 shadow nullok try_first_pass use_authtok
password    sufficient                                   pam_sss.so use_authtok
password    required                                     pam_deny.so

session     optional                                     pam_keyinit.so revoke
session    optional                                     pam_systemd.so
session     [success=1 default=ignore]                   pam_succeed_if.so service in crond quiet use_uid
session     required                                     pam_unix.so
session     optional                                     pam_sss.so
```
