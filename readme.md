## iFactory3D version of the Kiri:Moto Slicer.

More informations in the original repository:
https://github.com/GridSpace/grid-apps

and here:
https://grid.space/kiri/

Donations to the original creator go to:
https://www.paypal.com/paypalme/gridspace3d?locale.x=en_US

More informations on iFactory3D and Beltprinters:
https://ifactory3d.com/


## How to install it on a raspberry pi, to have a slicer dedicated to your printer:

## Testing Locally (with Docker):
git clone https://github.com/martinjohuber/grid-apps

cd grid-apps

docker compose -f src/dock/compose.yml up

## Testing Locally (with NodeJS):
Check your node version and npm version, mine is for example:

npm -v

9.2.0

node -v

v18.19.0

## Install with:
git clone https://github.com/martinjohuber/grid-apps

cd grid-apps

npm i

sudo npm install -g @gridspace/app-server

gs-app-server --debug

to start a local instance of the apps. then use a browser to open localhost:8080/kiri

Alternatively, if you are using a packaged version of npm that ships with a Linux distribution, but still want to install in your home directory, you can use
npm config set prefix ~/.local

If gs-app-server is not found, then perhaps ~/.local/bin is not in your path. You can either add it to your path, or you can run:
~/.local/bin/gs-app-server --debug

You can now access your environment of grid-apps by going to localhost:8080/kiri

Other Start Options <br/>
<code>gs-app-server</code>

serves code as obfuscated, compressed bundles. this is the mode used to run on a public web site.

requires node.js 12+

## installation pm2 (process manager)

<code>sudo npm install pm2 -g</code>

startup service einrichten (autostart on reboot) <br/>
<code>pm2 startup</code>

You have to run this command as root. Execute the following command: <br/>
<code>sudo su -c "env PATH=$PATH:/home/unitech/.nvm/versions/node/v14.3/bin pm2 startup <distribution> -u <user> --hp <home-path></code>

Navigate to the grid-apps folder: <br/>
<code>pm2 start gs-app-server</code>

Last but not least save the app list to restart on reboot <br/>
<code>pm2 save</code>


