# Media Parser Client

This is a client for the [Media Parser](https://github.com/jag-k/media-parser) project.

## Installation

```bash
poetry add git+https://github.com/jag-k/media-parser-client.git
```

## Usage

```python
from media_parser import Client, FeedbackTypes

client = Client("http://localhost:8000")


async def main():
    # Get all media
    media = await client.parce("https://www.youtube.com/watch?v=9bZkp7q19f0", user="jag-k")
    print(media)

    # If media is incorrect, you can send feedback
    await client.send_feedback(media, "jag-k", FeedbackTypes.wrong_media)


if __name__ == '__main__':
    import asyncio

    asyncio.run(main())

```

## License

[MIT](LICENSE)
