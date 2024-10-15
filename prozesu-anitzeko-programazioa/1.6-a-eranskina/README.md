---
description: Prozesuak natiboki Linuxen - C
---

# 1.6 A Eranskina

Lehenik eta behin, Linuxen programatzeko C lengoaiarentzat lan-ingurunea prestatuko dugu programa hauek instalatzen:

| Visual Studio Code                                                                                                                                                                                                                                                                                                                                                                                    | Dev-C++                                                                                                                                                                                                                                                                                                                                                                                                  | CLion                                                                                                                                                                                                                                                                                                                                                                                          |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <img src="https://urkoapunteak.gitbook.io/~gitbook/image?url=https%3A%2F%2F737682242-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F1fkTiBk8oxbo9vMUdfVS%252Fuploads%252Fgit-blob-05871a0c97879005c4fefcedd59aa7d613b2ebfd%252Fvscode_iconn.png%3Falt%3Dmedia&#x26;width=40&#x26;dpr=4&#x26;quality=100&#x26;sign=5431a835&#x26;sv=1" alt="" data-size="line"> | <img src="https://urkoapunteak.gitbook.io/~gitbook/image?url=https%3A%2F%2F737682242-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F1fkTiBk8oxbo9vMUdfVS%252Fuploads%252Fgit-blob-b3428d84415f3abcadcd8182eef5e40a24328c8d%252FDev-c%252B%252B.png%3Falt%3Dmedia&#x26;width=40&#x26;dpr=4&#x26;quality=100&#x26;sign=8638630a&#x26;sv=1" alt="" data-size="line"> | <img src="https://urkoapunteak.gitbook.io/~gitbook/image?url=https%3A%2F%2F737682242-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F1fkTiBk8oxbo9vMUdfVS%252Fuploads%252Fgit-blob-629151a10c2dde2548c31ac8ec9d883d46f3b9fd%252FCLion.png%3Falt%3Dmedia&#x26;width=40&#x26;dpr=4&#x26;quality=100&#x26;sign=2cba7ada&#x26;sv=1" alt="" data-size="line"> |

Aukeratutako sistema eragilea Linux banaketako Ubuntu izango da.

<img src="https://urkoapunteak.gitbook.io/~gitbook/image?url=https%3A%2F%2F737682242-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F1fkTiBk8oxbo9vMUdfVS%252Fuploads%252Fgit-blob-fbffc5f851ef3f4446c518c83ff36ae3023b5061%252FLogo%2520Ubuntu.png%3Falt%3Dmedia&#x26;width=177&#x26;dpr=4&#x26;quality=100&#x26;sign=bcaf8b5c&#x26;sv=1" alt="" data-size="line">

## Prozesuak Linuxen

Martxan dauden prozesuak ikusteko, `ps` komandoa erabil dezakegu eta aukerako atributuen arabera, informazio gehiago edo gutxiago emango digu. Adibidez: `ps`, `ps -f`, edo `ps -af`.

{% tabs %}
{% tab title="ps" %}
```bash
erab@ekipoa:~$ ps
PID TTY          TIME CMD
3170 pts/1    00:00:00 bash
3179 pts/1    00:00:00 ps
```
{% endtab %}

{% tab title="ps -f" %}
```bash
erab@ekipoa:~$ ps -f
UID          PID    PPID  C STIME TTY          TIME CMD
erab        3170    3144  0 09:05 pts/1    00:00:00 bash
erab        3186    3170  0 09:05 pts/1    00:00:00 ps -f
```
{% endtab %}

{% tab title="ps -af" %}
```bash
erab@ekipoa:~$ ps -AF
UID          PID    PPID  C    SZ   RSS PSR STIME TTY          TIME CMD
root           1       0  0 41647 11760   0 08:57 ?        00:00:03 /sbin/init splash
root           2       0  0     0     0   0 08:57 ?        00:00:00 [kthreadd]
root           3       2  0     0     0   0 08:57 ?        00:00:00 [rcu_gp]
root           4       2  0     0     0   0 08:57 ?        00:00:00 [rcu_par_gp]
root           5       2  0     0     0   0 08:57 ?        00:00:00 [netns]
root           7       2  0     0     0   0 08:57 ?        00:00:00 [kworker/0:0H-events_highpri]
root           8       2  0     0     0   0 08:57 ?        00:00:03 [kworker/u4:0-events_unbound]
root           9       2  0     0     0   0 08:57 ?        00:00:01 [kworker/0:1H-events_highpri]
root          10       2  0     0     0   0 08:57 ?        00:00:00 [mm_percpu_wq]
root         302       1  0  6619  6732   0 08:57 ?        00:00:00 /lib/systemd/systemd-udevd
root         342       2  0     0     0   0 08:57 ?        00:00:00 [iprt-VBoxWQueue]
root         352       2  0     0     0   0 08:57 ?        00:00:02 [kworker/u4:5-events_unbound]
root         361       2  0     0     0   0 08:57 ?        00:00:00 [cryptd]
systemd+     438       1  0  3706  6140   0 08:57 ?        00:00:01 /lib/systemd/systemd-oomd
systemd+     439       1  0  6348 13764   0 08:57 ?        00:00:00 /lib/systemd/systemd-resolved
root         560       1  0 62236  8088   0 08:57 ?        00:00:00 /usr/libexec/accounts-daemon
......................................
erab        1900    1130  0 133231 69192  0 08:58 ?        00:00:00 /usr/libexec/gsd-xsettings
erab        1907    1269  0 718733 66576  1 08:58 ?        00:00:02 gjs /usr/share/gnome-shell/extensions/ding@rastersoft.com/ding
erab        1954    1130  0 50885 25724   0 08:58 ?        00:00:00 /usr/libexec/ibus-x11
erab        1988    1130  0 42966  6832   1 08:58 ?        00:00:00 /usr/libexec/gvfsd-metadata
root        1999       1  0 115270 85612  0 08:58 ?        00:00:04 /usr/libexec/fwupd/fwupd
erab        2358    1248  0 125730 30440  1 08:59 ?        00:00:00 update-notifier
urko        2910    1130  8 178547 197464 1 09:00 ?        00:00:35 /usr/bin/python3 /usr/bin/update-manager --no-update --no-focu
root        2980       1  2 54503 111824  0 09:01 ?        00:00:07 /usr/bin/python3 /usr/sbin/aptd
_apt        3064    2980 22  8341  9292   1 09:01 ?        00:01:14 /usr/lib/apt/methods/http
root        3134       2  0     0     0   0 09:03 ?        00:00:00 [kworker/0:0-events]
erab        3144    1130  2 177207 58548  0 09:05 ?        00:00:03 /usr/libexec/gnome-terminal-server
erab        3170    3144  0  4947  5216   1 09:05 pts/1    00:00:00 bash
erab        3192    3170  0  5350  1604   1 09:07 pts/1    00:00:00 ps -AF
```
{% endtab %}
{% endtabs %}

Ikusten duzunez, ps  aginduari parametro ezberdinak ematean, makinan martxan dauden prozesuei buruzko informazio gehiago edo gutxiago lortu dezakegu. Irteeratik, prozesuaren PID (Process ID) eta PPID (Parent Process ID) ezagutzea erabilgarria da, prozesuaren IDa eta gurasoen IDa identifikatzeko beste eragiketa batzuetarako. Beste balio interesgarri bat UID (User ID) da, hau da, prozesua gauzatzen duen erabiltzailearen ID.
