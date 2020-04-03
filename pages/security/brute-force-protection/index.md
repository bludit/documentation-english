# Brute Force Protection
<!-- position: 2 -->

## What is a Brute Force Attack?
This kind of attack consists of an attacker trying many passwords or passphrases with the hope of eventually guessing correctly -Wiki.

## How this works?
Bludit provides brute force protection to mitigate this kind of attack, and this protection is enabled by default.

For each failure to log in, Bludit adds the IP of the user who failed to authenticate to a blacklist. When the user fails for a number of times, Bludit blocks the offending IP for a period of time, and the user can't log in until the block has expired.

## Class and Object
There is a `Security Object` called `$security`, and the class of the object is `/bl-kernel/security.class.php`. Take a look at the variables inside the class.

<pre><code data-language="php">
private $dbFields = array(
    'minutesBlocked'=>5,
    'numberFailuresAllowed'=>10,
    'blackList'=>array()
);
</code></pre>

- `minutesBlocked`: Amount of minutes the IP is going to be blocked.
- `numberFailuresAllowed`: Number of failed attempts for the block to trigger.
- `blackList`: The list of IPs blocked.

<div class="note">
<div class="title">Note</div>
You can change these values to your own values.
</div>
