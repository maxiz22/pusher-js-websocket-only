This fork is 1:1 of recent/stable Pusher, except that is manually going to have "lives" set to `99999` instead of `2`

Normally, with Pusher, it will revert to another connection type (like XHR streaming), but custom Pusher backends don't support these, so its more useful to force it to always use websockets. It's a questionable decision to forcibly switch the session to XHR streaming because websockets failed twice. Mobile browsers will fail after backgrounding, so any kind of SPA in use with an open-source backend will be basically unworkable without a custom solution like this.

# Install
Simply run:
```
npm install https://github.com/findmate/pusher-js-websocket-only
```

It will add the entry in package.json as follows:

```
"pusher-js": "git+https://github.com/findmate/pusher-js-websocket-only.git",
```

And you will be able to use Pusher completely as normally, except it will never use any connection type except Websockets.
