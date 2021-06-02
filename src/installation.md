# Installation

## Step 1 - Install the collector package

The first step is installing our collector package into the Laravel app you wish to monitor.

<pre class="command-line language-bash" data-prompt="$"><code>composer require qmonitor/laravel-qmonitor-collector</code></pre>

> Note: if you are using Laravel 5.x or 6.x you will need to use version 1.x of the collector package

<pre class="command-line language-bash" data-prompt="$"><code>composer require qmonitor/laravel-qmonitor-collector:^2.0</code></pre>

## Step 2 - Setup

### Create account
If you haven't already, create an account on [qmonitor.io](https://app.qmonitor.io/register).

### Run the artisan setup command
Run the artisan setup command to initialize and start monitoring queue jobs in your app. This command is specific to your application.

<pre class="command-line language-bash" data-prompt="$"><code>php artisan qmonitor:setup <span class="pl-k">&lt;</span>setup-key<span class="pl-k">&gt;</span></code></pre>

This command will handle a few things for you, like generating a payload signing secret, publishing the package config file and adding some config keys to your .env file.

> **IMPORTANT!** This command will autogenerate a secret used to sign the requests and make sure the payload is received by our servers without being tampered with. If you're monitoring queues from multiple environments, simply copy the `QMONITOR_APP_ID` and `QMONITOR_SECRET` keys to your other `.env` files.

After this step is complete, your setup is complete and your app dashboard will start populating with data as soon we start receiving queue job events from your Laravel application.



