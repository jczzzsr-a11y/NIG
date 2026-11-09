import json

config = {
    "platform": "energy.com",
    "feed_type": "live_interactive",
    "stream_url": "wss://stream.energy.com/live/feed",
    "resolution": "1080p",
}

print(json.dumps(config, indent=4))
