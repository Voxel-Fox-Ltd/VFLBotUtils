.. raw:: html

   <style>
      .class > dt > .property {
         display: none !important;
      }
   </style>

Config Files
===========================

The config file for the bot is one of the few *required* changes from default Discord.py, meaning that keeping your config file correct and up-to-date pretty important.

Bot Config File
-----------------------------------------

.. class:: BotConfig

   .. attribute:: token
      :type: str

      The token that the bot should run with.

   .. attribute:: owners
      :type: list

      A list of the IDs for the owners of the bot. People in this list will bypass all command check failures, and will receive DMs from the bot when it hits an error if :attr:`BotConfig.dm_uncaught_errors` is enabled.

   .. attribute:: dm_uncaught_errors
      :type: bool

      Whether or not the bot should DM the owners a traceback when it hits an unhandled error.

   .. attribute:: user_agent
      :type: str

      A simple constant that you can access with :attr:`voxelbotutils.Bot.user_agent`.

   .. attribute:: default_prefix
      :type: str, list

      The prefix that the bot should use by default. Can be either a string or a list. The bot will always respond to its user and role mention.

   .. attribute:: support_guild_id
      :type: int

      The ID of your support guild. Will be used in :func:`voxelbotutils.Bot.fetch_support_guild`.

   .. attribute:: bot_support_role_id
      :type: int

      The ID of your bot support role. Will be used in :func:`voxelbotutils.checks.is_bot_support`.

   .. attribute:: guild_settings_prefix_column
      :type: str

      The column of your prefix in the :code:`guild_settings` table. You don't need to change this from :code:`prefix` unless you're running multiple bots from the same directory.

   .. attribute:: cached_messages
      :type: int

      The number of messages to keep cached in the bot.

   .. class:: event_webhook

      A simple webhook that recieves event pings.

      .. attribute:: event_webhook_url
         :type: str

         A Discord webhook URL to send event notifications to.

      .. class:: events

         .. attribute:: guild_join
            :type: bool

         .. attribute:: guild_remove
            :type: bool

         .. attribute:: shard_connect
            :type: bool

         .. attribute:: shard_disconnect
            :type: bool

         .. attribute:: shard_ready
            :type: bool

         .. attribute:: bot_ready
            :type: bool

         .. attribute:: unhandled_error
            :type: bool

   .. class:: intents

      The intents that you want enabled on the bot.

      .. attribute:: guilds
         :type: bool

      .. attribute:: members
         :type: bool

      .. attribute:: bans
         :type: bool

      .. attribute:: emojis
         :type: bool

      .. attribute:: integrations
         :type: bool

      .. attribute:: webhooks
         :type: bool

      .. attribute:: invites
         :type: bool

      .. attribute:: voice_states
         :type: bool

      .. attribute:: presences
         :type: bool

      .. attribute:: guild_messages
         :type: bool

      .. attribute:: dm_messages
         :type: bool

      .. attribute:: guild_reactions
         :type: bool

      .. attribute:: dm_reactions
         :type: bool

      .. attribute:: guild_typing
         :type: bool

      .. attribute:: dm_typing
         :type: bool

   .. class:: help_command

      Attributes for the help command.

      .. attribute:: dm_help
         :type: bool

         Whether or not the help command should be DM'd to the user by default.

      .. attribute:: content
         :type: str

         Additional content to be sent along with the bot's help embed.

   .. class:: bot_listing_api_keys

      API keys that the bot uses internally to keep the bot listings up-to-date.

      .. attribute:: topgg_token

      .. attribute:: discordbotlist_token

   .. class:: command_data

      Simple data for call/response commands.

      .. attribute:: website_link
         :type: str

         A link to your website.

      .. attribute:: guild_invite
         :type: str

         A link to your guild.

      .. attribute:: github_link
         :type: str

         A link to the bot's git page.

      .. attribute:: donate_link
         :type: str

         A link where users can donate to you.

      .. attribute:: echo_command_enabled
         :type: bool

         Whether or not the echo command is enabled.

      .. attribute:: stats_command_enabled
         :type: bool

         Whether or not the stats command is enabled.

      .. attribute:: vote_command_enabled
         :type: bool

         Whether or not the vote command is enabled - this will link to your Top.gg page where users can vote for the bot.

      .. attribute:: updates_channel_id
         :type: int

         The channel ID for an announcement channel where users can receive updates about your bot.

      .. attribute:: info
         :type: str

         Simple information about your bot that gets output on using the :code:`!info` command.

   .. class:: oauth

      Oauth data used to build the bot's invite link.

      .. attribute:: enabled
         :type: bool

         Whether or not the invite command is enabled.

      .. attribute:: base
         :type: str

         The base of your invite link. You probably don't need to change this.

      .. attribute:: response_type
         :type: str

         The response type that the authorize page gives you. Unless you're doing things with oauth, youc an leave this alone.

      .. attribute:: redirect_uri
         :type: str

         Where the user id redirected to when they authorize your bot.

      .. attribute:: client_id
         :type: str

         The client ID for your application.

      .. attribute:: scope
         :type: str

         A space-seperated list of scopes that your invite command will use.

      .. attribute:: permissions
         :type: list

         A list of the permissions that the invite command should use.

   .. class:: database

      The configuration for your Postgres connection.

      .. attribute:: enabled
         :type: bool

         Whether or not to connect to the database on startup.

      .. attribute:: user
         :type: str

         The user that you want to connect with,

      .. attribute:: password
         :type: str

         The password of that user.

      .. attribute:: database
         :type: str

         The database that you want to connect to.

      .. attribute:: host
         :type: str

         The host IP/URL that you want to connect to.

      .. attribute:: port
         :type: int

         The port that your Postgres instance is running on.

   .. class:: redis

      The configuration for you Redis connection.

      .. attribute:: enabled
         :type: bool

         Whether or not to connect to reids on startup.

      .. attribute:: host
         :type: str

         The host IP/URL that you want to connect to.

      .. attribute:: port
         :type: int

         The port that your Redis instance is running on.

      .. attribute:: db
         :type: int

         The database that you want to connect to.

   .. class:: embed

      Details for auto-embedding all bot responses.

      .. attribute:: enabled
         :type: bool

         Whether or not you want to automatically embed bot responses.

      .. attribute:: content
         :type: str

         Additional content to be sent with the bot response.

      .. attribute:: colour
         :type: int

         The colour of the embed to be sent. If the value given is :code:`0`, then the colour will be random.

      .. attribute:: footer
         :type: list

         A list of footer objects to be added to the bot. These should contain :code:`text` and :code:`amount` attributes. A footer will be picked randomly from the list.

      .. class:: author

         The author that will get added to the embed.

         .. attribute:: enabled
            :type: bool

            Whether or not you want to add an author to your embed.

         .. attribute:: name
            :type: str

            The name of the author field.

         .. attribute:: url
            :type: str

            The URL that the author field should point to.

   .. class:: presence

      The presence that the bot should use when online.

      .. attribute:: activity_type
         :type: str

         The type of activity that the bot should be using.

      .. attribute:: text
         :type: str

         The text given to the activity.

      .. attribute:: status
         :type: str

         The status of the bot while online.

      .. attribute:: include_shard_id
         :type: bool

         Whether or not the shard ID of the bot should be included in its presence. Only applies after you identify with more than one shard.

      .. class:: streaming

         A set of information that lets you automatically update the bot's presence when a given user starts streaming on Twitch.tv. You can get client information `from here<https://dev.twitch.tv/console/apps>`_.

         .. attribute:: twitch_usernames
            :type: list

            A list of usernames that you want to check for.

         .. attribute:: twitch_client_id
            :type: str

            Your Twitch client ID.

         .. attribute:: twitch_client_secret
            :type: str

            Your Twitch client secret.

   .. class:: upgrade_chat

      A set of information that lets you check for purchases made with Upgrade.Chat. You can get client information `from here<https://upgrade.chat/developers>`_.

      .. attribute:: client_id
            :type: str

            Your Upgrade.Chat client ID.

      .. attribute:: client_secret
            :type: str

            Your Upgrade.Chat client ID.

   .. class:: statsd

      Your Datadog stats information.

      .. attribute:: host
         :type: str

         The host that you want to post information to.

      .. attribute:: port
         :type: int

         The port that you want to connect to.

      .. class:: constant_tags

         The tags that you want to send with each post. Most helpful is the bot name.

         .. attribute:: service
            :type: str

            An identifier for this set of stats - required for the information posting to be enabled.

Website Config File
--------------------------------------

.. class:: WebsiteConfig

   .. attribute:: website_base_url

   .. attribute:: login_url

   .. attribute:: routes

   .. attribute:: oauth_scopes

   .. class:: discord_bot_configs

      .. attribute:: bot

   .. class:: oauth

      .. attribute:: client_id

      .. attribute:: client_secret

   .. class:: database

      .. attribute:: enabled

      .. attribute:: user

      .. attribute:: password

      .. attribute:: database

      .. attribute:: host

      .. attribute:: port

   .. class:: reids

      .. attribute:: enabled

      .. attribute:: host

      .. attribute:: port

      .. attribute:: db
