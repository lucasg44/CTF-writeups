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

When looking at the file TimeController.php, I saw it was a 1 for 1 copy of the file Tri Wanda Septian provided in the resource above

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
