0x13. Firewall

We can see that the connection never succeeds, so after some time I just use ctrl+c to kill the process.

This can be used not just for this exercise, but for any debugging situation where two pieces of software need to communicate over sockets.

Note that the school network is filtering outgoing connections (via a network-based firewall), so you might not be able to interact with certain ports on servers outside of the school network. To test your work on web-01, please perform the test from outside of the school network, like from your web-02 server. If you SSH into your web-02 server, the traffic will be originating from web-02 and not from the school’s network, bypassing the firewall.

Warning!
Containers on demand cannot be used for this project (Docker container limitation)

Be very careful with firewall rules! For instance, if you ever deny port 22/TCP and log out of your server, you will not be able to reconnect to your server via SSH, and we will not be able to recover it. When you install UFW, port 22 is blocked by default, so you should unblock it immediately before logging out of your server.

Tasks
0. Block all incoming traffic but
mandatory
Score: 0.0% (Checks completed: 0.0%)
Let’s install the ufw firewall and setup a few rules on web-01.

Requirements:

The requirements below must be applied to web-01 (feel free to do it on lb-01 and web-02, but it won’t be checked)
Configure ufw so that it blocks all incoming traffic, except the following TCP ports:
22 (SSH)
443 (HTTPS SSL)
80 (HTTP)
Share the ufw commands that you used in your answer file

1. Port forwarding
#advanced
Score: 0.0% (Checks completed: 0.0%)
Firewalls can not only filter requests, they can also forward them.

Requirements:

Configure web-01 so that its firewall redirects port 8080/TCP to port 80/TCP.
Your answer file should be a copy of the ufw configuration file that you modified to make this happen
Terminal in web-01:
