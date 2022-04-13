# Installation

## Step 1 - Install the collector package

The first step is installing our collector package into the Laravel app you wish to monitor.

<pre class="command-line language-bash" data-prompt="$"><code>composer require qmonitor/laravel-qmonitor-collector</code></pre>

Depending on your Laravel version you're running, you'll need to match with one of our versions of the collector package:
| **Laravel**  |  **laravel-qmonitor-collector** |
|---|---|
| 5.7  | ^1.0  |
| 5.8  | ^1.0  |
| 6.x  | ^1.0  |
| 7.x  | ^2.0 |
| 8.x  | ^2.0 |
| 9.x  | ^3.0 |

To install a specific version, you can use the following command:
<pre class="command-line language-bash" data-prompt="$"><code>composer require qmonitor/laravel-qmonitor-collector:^1.0</code></pre>


## Step 2 - Setup

### Create account
If you haven't already, create an account on [qmonitor.io](https://app.qmonitor.io/register).

### Run the artisan setup command
Run the artisan setup command to initialize and start monitoring queue jobs in your app. This command is specific to your application.

<pre class="command-line language-bash" data-prompt="$"><code>php artisan qmonitor:setup <span class="pl-k">&lt;</span>setup-key<span class="pl-k">&gt;</span></code></pre>

This command will handle a few things for you:
 - it will generate a signing secret and send it to the setup endpoint;
 - it will publish the qmonitor.php config file into your Laravel app configs folder;
 - it will add the credential keys and values to the `.env` file;
 - it will add the credential keys to your the `.env.example` file;
 - it will send a heartbeat to [qmonitor.io](https://qmonitor.io).

> **IMPORTANT!** This command will autogenerate a secret used to sign the requests and make sure the payload is received by our servers without being tampered with. If you're monitoring queues from multiple environments, simply copy the `QMONITOR_APP_ID` and `QMONITOR_SECRET` keys to your other `.env` files.

After this step is complete, your setup is complete and your app dashboard will start populating with data as soon we start receiving queue job events from your Laravel application.



