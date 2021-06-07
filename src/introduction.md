# Introduction

## The Story
Laravel Queues are AWESOME! It's one of the best features in Laravel that I find myself using in 99% of the projects I work on. It takes care of those heavy, time-consuming, and request-blocking tasks, which enable us to build a smooth UX where the users don't have to spend their time looking at loading spinners and waiting for the pages to load or react to their input. Also pairs beautifully with the task scheduler to handle your behind-the-scenes magic.

In my experience, once set up, the queue jobs will just work and stay out of your hair. And will continue working unless something really bad happens to your app or your server. In which case, you'll probably hear from your error tracking or uptime monitoring solution. When a job fails, I'm usually notified by my error tracking service (cough cough <a href="https://www.honeybadger.io/" target="_blank" rel="noopener">Honeybadger</a>). You also have the option to set up failure notifications right within the job logic (I've never done that). But most of the time it will be quiet.

After a while, paranoia kicks in and I start thinking maybe it's too quiet. Are my queue workers running? Did the jobs run when they were supposed to? So I start investigating. If you're using <a href="https://laravel.com/docs/8.x/horizon" target="_blank" rel="noopener">Laravel Horizon</a> or have setup <a href="https://laravel.com/docs/8.x/telescope" target="_blank" rel="noopener">Laravel Telescope</a> to watch for your jobs in production, then all you have to do is go to the specific dashboard and check what's going on. You could also use <a href="https://ohdear.app/blog/scheduled-task-monitoring-now-available-to-all-our-users#monitoring-queues-and-jobs-health" target="_blank" rel="noopener">OhDear</a> which has a basic queue heartbeat check.

Like most of you fine people, I'm constantly building things when the start of a new side project is just one command away. Moreso, the dev agency I work for has been growing like crazy this past year, and the projects we're handling started to pile up and continue to grow.

Most of these apps are running queue jobs to handle file processing, interaction with third party services, sending notifications etc. I have a process of checking them once a week and make sure everything is up and running. If your queue jobs handle time-sensitive tasks, I imagine you'll check them even often than that.

The process of monitoring the queue jobs from all these apps became tedious. Having to jump through all these dashboards just to check that everything is in working order is time-consuming. Sometimes, I need to handover or pick up a project from another team and the queue monitoring details can get lost along the way. Now, you have to look up that Horizon custom path or which credentials to use to be authorized in the Telescope dashboard. Argghhh!!!

After a few weeks of everything working smoothly, you lay your guard down, thinking everything will continue working as it did in the past weeks. But that's when you start getting pocked by your users or clients about things not working as they should in the app. There's nothing more frustrating than that.

## Details

Qmonitor enables you to monitor queue tasks from all your Laravel apps. This package will collect and send data and telemetry to qmonitor.io from where you can then inspect and analyze your queue jobs.

How many times have you been caught out by tasks not running when they should, held up by other tasks, or simply timing out?

Qmonitor.io installs as a package into your application and reports back any time your queue jobs run, automatically.

There is no need for you to configure individual monitors, send HTTP requests, or change your application code. Just follow the configuration steps and you'll be up and running in no time.
