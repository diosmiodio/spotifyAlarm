
So I made this script because I'm utterly dependent on spotify and I wanted to setup a process of grabbing a random song from a playlist and using it to wake me up.
This is basically a collection of me grabbing random bits and pieces and making them make sense to together to work.

## Preparing the Script.
to setup the script to use your playlist youre going to have to do the following

1. Right click on your desired playlist
2. Go to Share > Copy Spotify URI
3. This will give you a link that looks like this `spotify:user:1262074972:playlist:0e17t6YdVz9KfHN1OwJwS4`
4. Open up your AppleScript Editor & copy or open the `.scpt` file in this repository.
5. Paste the copied Spotify URI at the top of the script within the quotation marks `set playlist to "COPY YOUR PLAYLIST URI HERE"`
6. Save the script

## Running the Script as an Alarm
1. Open up your Terminal Application
2. Type in `crontab -e` and press enter.
3. Press the "i" key on your keyboard (this takes you into "insert" mode)
4. Set the time you want the script to run (p.s. it reads military time)

for clarity, I'm providing a chart below showing the syntax of the command
~~~~
┌───────────── minute (0 - 59)'
│ ┌───────────── hour (0 - 23)'
│ │ ┌───────────── day of month (1 - 31)
│ │ │ ┌───────────── month (1 - 12)
│ │ │ │ ┌───────────── day of week (0 - 6) (Sunday to Saturday;
│ │ │ │ │                                       7 is also Sunday on some systems)
│ │ │ │ │
│ │ │ │ │
* * * * *  command_to_execute
~~~~
5. set your wake up time _(for this example, I'll set it to 6:00 AM)_
	* `0 6 * * * command_to_execute`
6. where it says command to execute, replace it with the path to your script. _i.e. Users/username/Documents/spotifyWakeUp.scpt_
7. press the esc key to stop editing
8. type in :wq! to exit and save

Thats it, now a crontab job is set to run your script at that time!
