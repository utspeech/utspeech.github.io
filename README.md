# utspeech.github.io

## Posting a new meeting

To post a new meeting, you first need to ensure that the site has an entry for
the speaker. Speakers are listed under `content/speakers/<speaker_id>`, where
`speaker_id` needs to be a unique identifier. To make it easier to determine at
a glance whether a speaker has been registered, I've followed the naming
convention `speaker_id = <last_name><count>`, where `last_name` is whatever
name(s) come last in the speaker's provided name and `count` is a count
starting at `0` to ensure uniqueness (e.g. the first "Smith" who presents is
`smith0`, the second is `smith1`, and so on).

If the speaker isn't already listed, call

``` sh
hugo new speakers/<speaker_id>
```

which will populate the file `content/speakers/<speaker_id>/_index.md` with
some default information. Edit that file directly with whatever info the
speaker has provided. The only necessary value is the speaker's name.

Once that's ready, it's time to create the meeting entry. To do so, start by
calling

``` sh
hugo new meetings/<date>-<speaker_id>.md
```

where `date` is the date of the presentation (*not the current date!*) in the
form `YYYY-MM-DD` and `speaker_id` is as before. The `<date>-<speaker_id>` is
also the meeting id. The meeting id format is more rigid than the speaker id
because the meeting id is also used to fill in some of the default information
of the meeting.

Open up `content/meetings/<meeting_id>.md` and modify the remaining defaults.
You can always update the values at a later date if you have more information.

Run your server locally via

``` sh
hugo server -D
```

Ensure the new meeting is listed on the main page and the "Meetings" tab,
the description looks okay when you click into it, and the speaker's page is
also correct. Once that's done, remove the line

``` yaml
draft: true
```

in the `content/meetings/<meeting_id>.md` file, commit, and push.

## To-Do

- Mugshots.
