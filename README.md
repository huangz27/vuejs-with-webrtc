# vuejs with webrtc
See [DEMO](https://165.22.99.104:8081/). Running on Digital Ocean.

If clicking the join button doesnt work, go to this [link](https://165.22.99.104:9002/) first (enable access to signaling server)
## Project setup (Frontend)
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

## Project setup (Setup Signaling Server)
https://github.com/muaz-khan/RTCMultiConnection

```
mkdir demo && cd demo

# install from NPM
npm install rtcmulticonnection

# or clone from github
git clone https://github.com/muaz-khan/RTCMultiConnection.git ./

# install all required packages
# you can optionally include --save-dev
npm install

#Run Signaling Server: open at port 9002 (defined in App.Vue) and --ssl for https
node server --port=9002 --ssl
```


### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
