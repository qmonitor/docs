# Console Commands

These are the the artisan commands that are available to you after the collector package has been installed:

## qmonitor:setup

This command handles the initial setup of your queue monitoring.

<pre class="command-line language-bash" data-prompt="$"><code>php artisan qmonitor:setup <span class="pl-k">&lt;</span>setup-key<span class="pl-k">&gt;</span></code></pre>

This command will handle a few things for you:
 - it will generate a signing secret and send it to the setup endpoint;
 - it will publish the qmonitor.php config file into your Laravel app configs folder;
 - it will add the credential keys and values to the `.env` file;
 - it will add the credential keys to your the `.env.example` file;
 - it will send a heartbeat to [qmonitor.io](https://qmonitor.io).

### IMPORTANT!
This command will autogenerate and send to us a secret used to sign the requests and make sure the payloads are not being tampered with in transit. If you're monitoring queues from multiple environments, make sure you use same signing secret in the `QMONITOR_SECRET` config.


## qmonitor:heartbeat

This command will dispatch a job that will send a heartbeat to our collector. The heartbeat ensures that your queue worker(s) are running and processing queue jobs as expected.

The heartbeats queue jobs will not show up in your App jobs list, but only in the Heartbeats section of your App dashboard.

<pre class="command-line language-bash" data-prompt="$"><code>php artisan qmonitor:heartbeat</code></pre>

## qmonitor:test

This command will dispatch a test queue job that will be picked up by our monitoring package and send to your app dashboard. These test jobs will shpw up as any other regular queue job in the App jobs list.

<pre class="command-line language-bash" data-prompt="$"><code>php artisan qmonitor:test</code></pre>
