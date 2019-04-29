#!/usr/bin/python3
from pydbus import SessionBus
from gi.repository import GLib
import sys
import os
import argparse

ICON_PLAY = ""
ICON_PAUSE = ""
ICON = ""
PATH=os.path.realpath(__file__)
TITLE_LENGTH = 25

parser = argparse.ArgumentParser()
parser.add_argument('--volume', type=int)
parser.add_argument('--playpause', action="store_true")
args= parser.parse_args()

bus = SessionBus()
try:
    Player = bus.get(
        "org.kde.plasma.browser_integration",
        "/org/mpris/MediaPlayer2"
    )
except GLib.Error:
    exit()



if Player.PlaybackStatus != "Stopped":
    if args.volume != None:
        vol = Player.Volume
        Player.Volume = vol + (args.volume * 0.1)
        exit()
    if args.playpause:
        Player.PlayPause()
        exit()
    if Player.PlaybackStatus=="Playing":
        ICON = ICON_PAUSE
    elif Player.PlaybackStatus=="Paused":
        ICON = ICON_PLAY
    title = Player.Metadata["xesam:title"]
    output="%{A1:" + PATH + " --playpause:}"+ ICON + "%{A} " + (title[:TITLE_LENGTH] +"..." if len(title) > TITLE_LENGTH and TITLE_LENGTH>0 else title)
    print(output)
else:
    print("")
