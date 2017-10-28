# Title: Brute Force Protection
<!-- Position: 2 -->
---
## What is Brute Force Attack?
Consists of an attacker trying many passwords or passphrases with the hope of eventually guessing correctly -Wiki.

## How this works?
Bludit provides a brute force protection to mitigate this kind of attack and is enabled by default.

For each fail on the login, Bludit adds the IP of the user who failed to authenticate on a blacklist; When the user fails for a number of times, Bludit blocks his IP for a period of time and the user can't log in until the blocked expired.

## Class and Object
There is a `Security Object` called `$Security` and the class of the object is `/bl-kernel/security.class.php`. Take a look at the variables inside the class.

<pre><code data-language="php">
private $dbFields = array(
    'minutesBlocked'=>5,
    'numberFailuresAllowed'=>10,
    'blackList'=>array()
);
</code></pre>

- `minutesBlocked`: Amount of minutes the IP is going to be blocked.
- `numberFailuresAllowed`: Number of attempt until be blocked.
- `blackList`: The list of IPs blocked.

<div class="note">
<div class="title">Note</div>
You can change this values for your own values.
</div>
