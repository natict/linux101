1. How many network interfaces do you have?
    1. What are their supported link mode? (e.g. 100Mbps? 1Gbps?)
    2. Are they connected (i.e. Link Detected)?
    3. Do they have an IP address associated with them? what is the network's netmask?
    4. What is the default gateway for this interface?
2. List the processes listening on IPv4 TCP ports
    1. Repeat for UDP ports
3. Use `curl -v` to connect to some web server
    1. What is the HTTP version? what is the response code?
    2. Why does the HTTP client need the Content-Length header?
    3. Is there an equivalent of the Content-Length header for headers? How does the client know where the headers end?
4. Start a HTTP server with python: `python -m SimpleHTTPServer 80`
    1. What happens when you run that command as a regular user? why?
    2. Read about the hosts file (`man 5 hosts`)
        1. Cause all `google.com` traffic to redirect to your python HTTP server
        2. Test that with `curl -v`
    3. Use `ss` to list your server process
5. Use tcpdump to capture only DNS traffic (i.e. UDP port 53)
    1. make sure to capture responses too!