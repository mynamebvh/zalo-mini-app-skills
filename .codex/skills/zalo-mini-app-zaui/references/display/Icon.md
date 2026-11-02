# Icon

> Source: https://docs.zaloplatforms.com/docs/MA/zaui/display/Icon

Last updated: 28/10/2026

```ts
import { Icon } from "zmp-ui";
```

Used to display an icon illustrating an action or state.

## Usage


### Props

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| children | string | No |  |
| icon | IconString | No | The key of the icon to display. See the list of all icons [here](/docs/MA/zaui/display/Icon).<br>It can be passed as a `string` or the `IconString` enum. When using the enum, the IDE will support an icon preview. Example: ![zi-search](data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZmlsbC1ydWxlPSJldmVub2RkIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiIGQ9Ik00LjA5OTkgOS45OTk5QzQuMDk5OSA2Ljc0MTQyIDYuNzQxNDIgNC4wOTk5IDkuOTk5OSA0LjA5OTlDMTMuMjU4NCA0LjA5OTkgMTUuODk5OSA2Ljc0MTQyIDE1Ljg5OTkgOS45OTk5QzE1Ljg5OTkgMTMuMjU4NCAxMy4yNTg0IDE1Ljg5OTkgOS45OTk5IDE1Ljg5OTlDNi43NDE0MiAxNS44OTk5IDQuMDk5OSAxMy4yNTg0IDQuMDk5OSA5Ljk5OTlaTTkuOTk5OSAyLjg5OTlDNi4wNzg2OCAyLjg5OTkgMi44OTk5IDYuMDc4NjggMi44OTk5IDkuOTk5OUMyLjg5OTkgMTMuOTIxMSA2LjA3ODY4IDE3LjA5OTkgOS45OTk5IDE3LjA5OTlDMTEuNjcyMyAxNy4wOTk5IDEzLjIwOTcgMTYuNTIxNiAxNC40MjMgMTUuNTU0MkMxNC40MjY3IDE1LjU1OCAxNC40MzA1IDE1LjU2MTggMTQuNDM0MyAxNS41NjU2TDE5LjQzNDMgMjAuNTY1NkMxOS43NDY3IDIwLjg3ODEgMjAuMjUzMiAyMC44NzgxIDIwLjU2NTYgMjAuNTY1NkMyMC44NzgxIDIwLjI1MzIgMjAuODc4MSAxOS43NDY3IDIwLjU2NTYgMTkuNDM0M0wxNS41NjU2IDE0LjQzNDNDMTUuNTYxOCAxNC40MzA1IDE1LjU1OCAxNC40MjY3IDE1LjU1NDIgMTQuNDIzQzE2LjUyMTYgMTMuMjA5NyAxNy4wOTk5IDExLjY3MjMgMTcuMDk5OSA5Ljk5OTlDMTcuMDk5OSA2LjA3ODY4IDEzLjkyMTEgMi44OTk5IDkuOTk5OSAyLjg5OTlaIiBmaWxsPSIjNzY3Njc2Ii8+Cjwvc3ZnPgo=) |
| size | number | No | The size of the icon, in px. |

## Design guidelines

###### Arrow

*zi\_arrow\_down*zi-arrow-down

*zi\_arrow\_left*zi-arrow-left

*zi\_arrow\_right*zi-arrow-right

*zi\_arrow\_up*zi-arrow-up

*zi\_auto*zi-auto

*zi\_auto\_solid*zi-auto-solid

*zi\_backup\_arrow\_solid*zi-backup-arrow-solid

*zi\_chevron\_double\_down*zi-chevron-double-down

*zi\_chevron\_double\_up*zi-chevron-double-up

*zi\_chevron\_down*zi-chevron-down

*zi\_chevron\_left*zi-chevron-left

*zi\_chevron\_left\_header*zi-chevron-left-header

*zi\_chevron\_right*zi-chevron-right

*zi\_chevron\_up*zi-chevron-up

*zi\_download*zi-download

*zi\_download\_solid*zi-download-solid

*zi\_reorder\_solid*zi-reorder-solid

*zi\_reply*zi-reply

*zi\_reply\_solid*zi-reply-solid

*zi\_retry*zi-retry

*zi\_retry\_solid*zi-retry-solid

*zi\_share*zi-share

*zi\_share\_external\_1*zi-share-external-1

*zi\_share\_external\_2*zi-share-external-2

*zi\_share\_solid*zi-share-solid

*zi\_unfold\_less*zi-unfold-less

*zi\_unfold\_more*zi-unfold-more

*zi\_upload*zi-upload

---

###### Basic

*zi\_add\_story*zi-add-story

*zi\_ban*zi-ban

*zi\_bullet\_solid*zi-bullet-solid

*zi\_check*zi-check

*zi\_check\_circle*zi-check-circle

*zi\_check\_circle\_solid*zi-check-circle-solid

*zi\_close*zi-close

*zi\_close\_circle*zi-close-circle

*zi\_close\_circle\_solid*zi-close-circle-solid

*zi\_copy*zi-copy

*zi\_delete*zi-delete

*zi\_drag\_indicator\_solid*zi-drag-indicator-solid

*zi\_filter*zi-filter

*zi\_filter\_solid*zi-filter-solid

*zi\_home*zi-home

*zi\_leave*zi-leave

*zi\_leave\_solid*zi-leave-solid

*zi\_list\_1*zi-list-1

*zi\_list\_2*zi-list-2

*zi\_minus\_circle*zi-minus-circle

*zi\_minus\_circle\_solid*zi-minus-circle-solid

*zi\_more\_diamond\_solid*zi-more-diamond-solid

*zi\_more\_grid*zi-more-grid

*zi\_more\_grid\_solid*zi-more-grid-solid

*zi\_more\_horiz*zi-more-horiz

*zi\_more\_horiz\_solid*zi-more-horiz-solid

*zi\_more\_vert*zi-more-vert

*zi\_plus*zi-plus

*zi\_plus\_circle*zi-plus-circle

*zi\_plus\_circle\_solid*zi-plus-circle-solid

*zi\_radio\_checked*zi-radio-checked

*zi\_radio\_unchecked*zi-radio-unchecked

*zi\_save\_to\_collection*zi-save-to-collection

*zi\_search*zi-search

*zi\_setting*zi-setting

*zi\_tune*zi-tune

---

###### Time

*zi\_calendar*zi-calendar

*zi\_calendar\_solid*zi-calendar-solid

*zi\_clock\_1*zi-clock-1

*zi\_clock\_1\_solid*zi-clock-1-solid

*zi\_clock\_2*zi-clock-2

*zi\_clock\_2\_solid*zi-clock-2-solid

*zi\_memory*zi-memory

*zi\_reminder*zi-reminder

*zi\_reminder\_delete*zi-reminder-delete

*zi\_reminder\_solid*zi-reminder-solid

---

###### Tools

*zi\_file*zi-file

*zi\_inbox*zi-inbox

*zi\_note*zi-note

*zi\_note\_delete*zi-note-delete

*zi\_pcline*zi-pcline

*zi\_poll*zi-poll

*zi\_poll\_solid*zi-poll-solid

*zi\_qrline*zi-qrline

*zi\_truyen\_file*zi-truyen-file

*zi\_wallpaper*zi-wallpaper

---

###### Edit

*zi\_edit*zi-edit

*zi\_edit\_delete*zi-edit-delete

*zi\_edit\_delete\_solid*zi-edit-delete-solid

*zi\_edit\_solid*zi-edit-solid

*zi\_edit\_text*zi-edit-text

*zi\_edit\_text\_solid*zi-edit-text-solid

*zi\_post*zi-post

---

###### Communication

*zi\_at*zi-at

*zi\_bubble\_multiselect*zi-bubble-multiselect

*zi\_call*zi-call

*zi\_call\_solid*zi-call-solid

*zi\_chat*zi-chat

*zi\_chat\_solid*zi-chat-solid

*zi\_grid\_solid*zi-grid-solid

*zi\_location*zi-location

*zi\_location\_solid*zi-location-solid

*zi\_mic*zi-mic

*zi\_quote*zi-quote

*zi\_quote\_solid*zi-quote-solid

*zi\_recall*zi-recall

*zi\_send\_solid*zi-send-solid

*zi\_user\_window\_solid*zi-user-window-solid

*zi\_video*zi-video

*zi\_video\_group*zi-video-group

*zi\_video\_solid*zi-video-solid

*zi\_wifi*zi-wifi

*zi\_wifi\_off*zi-wifi-off

---

###### Media

*zi\_add\_photo*zi-add-photo

*zi\_camera*zi-camera

*zi\_gallery*zi-gallery

*zi\_link*zi-link

*zi\_livestream*zi-livestream

*zi\_pause*zi-pause

*zi\_pause\_solid*zi-pause-solid

*zi\_photo*zi-photo

*zi\_photo\_search*zi-photo-search

*zi\_photo\_solid*zi-photo-solid

*zi\_play*zi-play

*zi\_play\_solid*zi-play-solid

---

###### User

*zi\_add\_member*zi-add-member

*zi\_add\_member\_solid*zi-add-member-solid

*zi\_add\_user*zi-add-user

*zi\_add\_user\_solid*zi-add-user-solid

*zi\_admin*zi-admin

*zi\_create\_group*zi-create-group

*zi\_create\_group\_solid*zi-create-group-solid

*zi\_group*zi-group

*zi\_group\_solid*zi-group-solid

*zi\_members*zi-members

*zi\_members\_solid*zi-members-solid

*zi\_stranger*zi-stranger

*zi\_stranger\_solid*zi-stranger-solid

*zi\_switch\_users*zi-switch-users

*zi\_switch\_users\_solid*zi-switch-users-solid

*zi\_user*zi-user

*zi\_user\_check*zi-user-check

*zi\_user\_circle*zi-user-circle

*zi\_user\_circle\_solid*zi-user-circle-solid

*zi\_user\_search*zi-user-search

*zi\_user\_search\_solid*zi-user-search-solid

*zi\_user\_settings*zi-user-settings

*zi\_user\_settings\_solid*zi-user-settings-solid

*zi\_user\_solid*zi-user-solid

---

###### Backup

*zi\_backup\_solid*zi-backup-solid

*zi\_backup\_success\_solid*zi-backup-success-solid

*zi\_backup\_warning\_solid*zi-backup-warning-solid

---

###### Bookmark

*zi\_bookmark*zi-bookmark

*zi\_bookmark\_delete*zi-bookmark-delete

*zi\_favorite\_list*zi-favorite-list

*zi\_heart*zi-heart

*zi\_heart\_solid*zi-heart-solid

*zi\_pin*zi-pin

*zi\_pin\_solid*zi-pin-solid

*zi\_star*zi-star

*zi\_star\_solid*zi-star-solid

*zi\_unpin*zi-unpin

---

###### Signage

*zi\_exclamation*zi-exclamation

*zi\_help\_circle*zi-help-circle

*zi\_info\_circle*zi-info-circle

*zi\_info\_circle\_solid*zi-info-circle-solid

*zi\_warning*zi-warning

*zi\_warning\_circle*zi-warning-circle

*zi\_warning\_circle\_solid*zi-warning-circle-solid

*zi\_warning\_solid*zi-warning-solid

---

###### Privacy

*zi\_hide*zi-hide

*zi\_key\_solid*zi-key-solid

*zi\_lock*zi-lock

*zi\_lock\_open\_solid*zi-lock-open-solid

*zi\_lock\_solid*zi-lock-solid

*zi\_notif*zi-notif

*zi\_notif\_off*zi-notif-off

*zi\_notif\_off\_solid*zi-notif-off-solid

*zi\_notif\_ring*zi-notif-ring

*zi\_shield\_solid*zi-shield-solid

*zi\_unhide*zi-unhide

*zi\_unlock*zi-unlock

*zi\_unlock\_solid*zi-unlock-solid
