# Power.profile
## os: Fedora

sch: https://www.google.com/search?q=fedora+power+disable+inactive+doesn%27t+work


https://discussion.fedoraproject.org/t/talk-gnome-suspends-after-15-minutes-of-user-inactivity-even-on-ac-power/80257  
https://discussion.fedoraproject.org/t/talk-gnome-suspends-after-15-minutes-of-user-inactivity-even-on-ac-power/80257?page=5

# Solution:
https://discussion.fedoraproject.org/t/gnome-suspends-after-15-minutes-of-user-inactivity-even-on-ac-power/79801  

quote:
>"Since Fedora 38, systems with the GNOME desktop environment suspend after 15 minutes of user inactivity, even when plugged in to the AC outlet. This affects new installs and some upgraded systems (depending whether you touched that setting in the past).
>
>This is due to an intentional change. To give it a better visibility, and because it might surprise many users and consider it a bug, it’s documented here."

## Login Screen Sleep Setting
quote:
>"If you’re at the login screen (e.g. after a system boot or a user logout), the default options are used (15 minutes timeout).
>
>Adjusting the login screen
>If you want to modify the login screen behavior, you can display the current login screen settings with this command:
>
>`sudo -u gdm dbus-run-session gsettings list-recursively org.gnome.settings-daemon.plugins.power | grep sleep`
>Which prints an output like this:
>```
>org.gnome.settings-daemon.plugins.power sleep-inactive-ac-timeout 900
>org.gnome.settings-daemon.plugins.power sleep-inactive-ac-type 'suspend'
>org.gnome.settings-daemon.plugins.power sleep-inactive-battery-timeout 900
>org.gnome.settings-daemon.plugins.power sleep-inactive-battery-type 'suspend'
>```
>The sleep-inactive-ac-timeout is the Plugged in option and sleep-inactive-battery-timeout is the On Battery Power option. The number is the delay in seconds. You can configure the values like this:
>
>`sudo -u gdm dbus-run-session gsettings set org.gnome.settings-daemon.plugins.power sleep-inactive-ac-timeout 1800`
>This sets the Plugged in delay to 1800 seconds, i.e. 30 minutes. You can use 0 to disable the automatic suspend completely. You can verify that the option was set by displaying the current values as described above.
