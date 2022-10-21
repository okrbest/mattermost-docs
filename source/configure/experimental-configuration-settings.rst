Experimental configuration settings
=====================================

Access the following experimental configuration settings:

- `Experimental System Console configuration settings <#experimental-system-console-configuration-settings>`__
- `Experimental Bleve configuration settings <#experimental-bleve-configuration-settings>`__
- `Experimental configuration settings for self-hosted deployments only <#experimental-configuration-settings-for-self-hosted-deployments-only>`__
- `Experimental job configuration settings <#experimental-job-configuration-settings>`__

----

Experimental System Console configuration settings
---------------------------------------------------

.. include:: ../_static/badges/allplans-cloud-selfhosted.rst
  :start-after: :nosearch:

Access the following experimental configuration settings in the System Console by going to **Experimental > Features**. 

AD/LDAP login button color
~~~~~~~~~~~~~~~~~~~~~~~~~~

Specify the color of the AD/LDAP login button for white labeling purposes. Use a hex code with a #-sign before the code. This setting only applies to the mobile apps.

+-------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"LoginButtonColor": ""`` with string input.                                       |
+-------------------------------------------------------------------------------------------------------------------------------+

AD/LDAP login button border color
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-pro-only.rst
  :start-after: :nosearch:

Specify the color of the AD/LDAP login button border for white labeling purposes. Use a hex code with a #-sign before the code. This setting only applies to the mobile apps.

+-------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"LoginButtonBorderColor": ""`` with string input.                                 |
+-------------------------------------------------------------------------------------------------------------------------------+

AD/LDAP login button text color
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-pro-only.rst
  :start-after: :nosearch:

Specify the color of the AD/LDAP login button text for white labeling purposes. Use a hex code with a #-sign before the code. This setting only applies to the mobile apps.

+-------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"LoginButtonTextColor": ""`` with string input.                                   |
+-------------------------------------------------------------------------------------------------------------------------------+

Change authentication method
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-pro-only.rst
  :start-after: :nosearch:

**True**: Users can change their sign-in method to any that is enabled on the server, either via their Profile or the APIs.

**False**: Users cannot change their sign-in method, regardless of which authentication options are enabled.

+-------------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"ExperimentalEnableAuthenticationTransfer": true`` with options ``true`` and ``false``. |
+-------------------------------------------------------------------------------------------------------------------------------------+

Link metadata timeout
~~~~~~~~~~~~~~~~~~~~~

Adds a configurable timeout for requests made to return link metadata. If the metadata is not returned before this timeout expires, the message will post without requiring metadata. This timeout covers the failure cases of broken URLs and bad content types on slow network connections.

+---------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"LinkMetadataTimeoutMilliseconds": 5000`` with numerical input.                     |
+---------------------------------------------------------------------------------------------------------------------------------+

Email batching buffer size
~~~~~~~~~~~~~~~~~~~~~~~~~~

Specify the maximum number of notifications batched into a single email.

+--------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``EmailBatchingBufferSize": 256`` with numerical input.                        |
+--------------------------------------------------------------------------------------------------------------------------+

Email batching interval
~~~~~~~~~~~~~~~~~~~~~~~~

Specify the maximum frequency, in seconds, which the batching job checks for new notifications. Longer batching intervals will increase performance.

+-----------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``EmailBatchingInterval": 30`` with numerical input.                        |
+-----------------------------------------------------------------------------------------------------------------------+

Email login button color
~~~~~~~~~~~~~~~~~~~~~~~~

Specify the color of the email login button for white labeling purposes. Use a hex code with a #-sign before the code. This setting only applies to the mobile apps.

+-------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"LoginButtonColor": ""`` with string input.                                       |
+-------------------------------------------------------------------------------------------------------------------------------+

Email login button border color
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Specify the color of the email login button border for white labeling purposes. Use a hex code with a #-sign before the code. This setting only applies to the mobile apps.

+-------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"LoginButtonBorderColor": ""`` with string input.                                 |
+-------------------------------------------------------------------------------------------------------------------------------+

Email login button text color
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Specify the color of the email login button text for white labeling purposes. Use a hex code with a #-sign before the code. This setting only applies to the mobile apps.

+-------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"LoginButtonTextColor": ""`` with string input.                                   |
+-------------------------------------------------------------------------------------------------------------------------------+

Enable account deactivation
~~~~~~~~~~~~~~~~~~~~~~~~~~~

**True**: Ability for users to deactivate their own account from **Settings > Advanced**. If a user deactivates their own account, they will get an email notification confirming they were deactivated.

**False**: Ability for users to deactivate their own account is disabled.

+--------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableUserDeactivation": false`` with options ``true`` and ``false``. |
+--------------------------------------------------------------------------------------------------------------------+

Enable automatic replies
~~~~~~~~~~~~~~~~~~~~~~~~~

**True**: Users can enable Automatic Replies in **Settings > Notifications**. Users set a custom message that will be automatically sent in response to Direct Messages.

**False**: Disables the Automatic Direct Message Replies feature and hides it from **Settings**.

+--------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"ExperimentalEnableAutomaticReplies": false`` with options ``true`` and ``false``. |
+--------------------------------------------------------------------------------------------------------------------------------+

Enable channel viewed websocket messages
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This setting determines whether ``channel_viewed WebSocket`` events are sent, which synchronize unread notifications across clients and devices. Disabling the setting in larger deployments may improve server performance.

+------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableChannelViewedMessages": true`` with options ``true`` and ``false``. |
+------------------------------------------------------------------------------------------------------------------------+

Enable default channel leave/join system messages
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This setting determines whether team leave/join system messages are posted in the default ``town-square`` channel.

**True**: Enables leave/join system messages in the default ``town-square`` channel.

**False**: Disables leave/join messages from the default ``town-square`` channel. These system messages won't be added to the database either.

+----------------------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"ExperimentalEnableDefaultChannelLeaveJoinMessages": true`` with options ``true`` and ``false``. |
+----------------------------------------------------------------------------------------------------------------------------------------------+

Enable hardened mode
~~~~~~~~~~~~~~~~~~~~~

**True**: Enables a hardened mode for Mattermost that makes user experience trade-offs in the interest of security.

**False**: Disables hardened mode.

Changes made when hardened mode is enabled:

- Failed login returns a generic error message instead of a specific message for username and password.
- If `multi-factor authentication (MFA) <https://docs.mattermost.com/onboard/multi-factor-authentication.html>`__ is enabled, the route to check if a user has MFA enabled always returns true. This causes the MFA input screen to appear even if the user does not have MFA enabled. The user may enter any value to pass the screen. Note that hardened mode does not affect user experience when MFA is enforced.
- Password reset does not inform the user that they can not reset their SSO account through Mattermost and instead claims to have sent the password reset email.
- Mattermost sanitizes all 500 errors before returned to the client. Use the supplied ``request_id`` to match user facing errors with the server logs.

+----------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"ExperimentalEnableHardenedMode": false`` with options ``true`` and ``false``. |
+----------------------------------------------------------------------------------------------------------------------------+

Enable preview features
~~~~~~~~~~~~~~~~~~~~~~~

**True**: Preview features can be enabled from **Settings > Advanced > Preview Pre-release features**.

**False**: Disables and hides preview features from **Settings > Advanced > Preview Pre-release features**.

+------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnablePreviewFeatures": true`` with options ``true`` and ``false``. |
+------------------------------------------------------------------------------------------------------------------+

Enable theme selection
~~~~~~~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-pro-only.rst
  :start-after: :nosearch:

*Available in legacy Enterprise Edition E10 and E20*

**True**: Enables the **Display > Theme** tab in **Settings** so users can select their theme.

**False**: Users cannot select a different theme. The **Display > Theme** tab is hidden in **Settings**.

+-----------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableThemeSelection": true`` with options ``true`` and ``false``. |
+-----------------------------------------------------------------------------------------------------------------+

Allow custom themes
~~~~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-pro-only.rst
  :start-after: :nosearch:

*Available in legacy Enterprise Edition E10 and E20*

**True**: Enables the **Display > Theme > Custom Theme** section in **Settings**.

**False**: Users cannot use a custom theme. The **Display > Theme > Custom Theme** section is hidden in **Settings**.

+--------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"AllowCustomThemes": true`` with options ``true`` and ``false``. |
+--------------------------------------------------------------------------------------------------------------+

Default theme
~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-pro-only.rst
  :start-after: :nosearch:

*Available in legacy Enterprise Edition E10 and E20*

Set a default theme that applies to all new users on the system.

+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"DefaultTheme": "default"`` with options ``"default"``, ``"organization"``, ``"mattermostDark"``, and ``"windows10"``. |
+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Enable tutorial
~~~~~~~~~~~~~~~~

**True**: Users are prompted with a tutorial when they open Mattermost for the first time after account creation.

**False**: The tutorial is disabled. Users are placed in Town Square when they open Mattermost for the first time after account creation.

+--------------------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableTutorial": true`` with options ``true`` and ``false``.                                  |
+--------------------------------------------------------------------------------------------------------------------------------------------+

Enable onboarding 
~~~~~~~~~~~~~~~~~~

**True**: New Mattermost users are shown key tasks to complete as part of initial onboarding.

**False**: User onboarding tasks are disabled. Users are placed in Town Square when they open Mattermost for the first time after account creation.

+--------------------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableOnboarding": true`` with options ``true`` and ``false``.                                |
+--------------------------------------------------------------------------------------------------------------------------------------------+

Enable user typing messages
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This setting determines whether "user is typing..." messages are displayed below the message box. Disabling the setting in larger deployments may improve server performance.

+---------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableUserTypingMessages": true`` with options ``true`` and ``false``. |
+---------------------------------------------------------------------------------------------------------------------+

User typing timeout
~~~~~~~~~~~~~~~~~~~~

This setting defines how frequently "user is typing..." messages are updated, measured in milliseconds.

+----------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"TimeBetweenUserTypingUpdatesMilliseconds": 5000`` with numerical input. |
+----------------------------------------------------------------------------------------------------------------------+

Primary team
~~~~~~~~~~~~~

The primary team of which users on the server are members. When a primary team is set, the options to join other teams or leave the primary team are disabled.

If the team URL of the primary team is https://example.mattermost.com/myteam/, then set the value to ``myteam`` in ``config.json``.

+-----------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"ExperimentalPrimaryTeam": ""`` with string input.                  |
+-----------------------------------------------------------------------------------------------------------------+

SAML login button color
~~~~~~~~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-pro-only.rst
  :start-after: :nosearch:

*Available in legacy Enterprise Edition E20*

Specify the color of the SAML login button for white labeling purposes. Use a hex code with a #-sign before the code. This setting only applies to the mobile apps.

+-------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"LoginButtonColor": ""`` with string input.                                       |
+-------------------------------------------------------------------------------------------------------------------------------+

SAML login button border color
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-pro-only.rst
  :start-after: :nosearch:

*Available in legacy Enterprise Edition E20*

Specify the color of the SAML login button border for white labeling purposes. Use a hex code with a #-sign before the code. This setting only applies to the mobile apps.

+-------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"LoginButtonBorderColor": ""`` with string input.                                 |
+-------------------------------------------------------------------------------------------------------------------------------+

SAML login button text color
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-pro-only.rst
  :start-after: :nosearch:

*Available in legacy Enterprise Edition E20*

Specify the color of the SAML login button text for white labeling purposes. Use a hex code with a #-sign before the code. This setting only applies to the mobile apps.

+-------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"LoginButtonTextColor": ""`` with string input.                                   |
+-------------------------------------------------------------------------------------------------------------------------------+

Use channel name in email notifications
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

**True**: Channel and team name appears in email notification subject lines. Useful for servers using only one team.

**False**: Only team name appears in email notification subject line.

+----------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"UseChannelInEmailNotifications": false`` with options ``true`` and ``false``. |
+----------------------------------------------------------------------------------------------------------------------------+

User status away timeout
~~~~~~~~~~~~~~~~~~~~~~~~

This setting defines the number of seconds after which the user's status indicator changes to "Away", when they are away from Mattermost.

+--------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"UserStatusAwayTimeout": 300`` with numerical input. |
+--------------------------------------------------------------------------------------------------+

Enable shared channels
~~~~~~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-selfhosted-only.rst
  :start-after: :nosearch:

*Available in legacy Enterprise Edition E20*

Shared channels enables the ability to establish secure connections between Mattermost instances, and invite secured connections to shared channels where secure connections can participate as they would in any public and private channel. Enabling shared channels functionality requires a server restart. 

+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| This feature's two ``config.json`` settings include ``"ExperimentalSettings:EnableSharedChannels": false`` with options ``true`` or ``false``, and ``"ExperimentalSettings:EnableRemoteClusterService": false`` with options ``true`` or ``false``. |
+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. note::

   - Both configuration settings must be enabled in order to share channels with secure connections. Only the **Enable Shared Channels** configuration option is available through the System Console.
   - System Admins for Cloud deployments can submit a request to have the ``EnableRemoteClusterService`` configuration setting enabled in their Cloud instance.

Enable app bar
~~~~~~~~~~~~~~~

This setting enables the Apps Bar and moves all Mattermost integration icons from the channel header to a vertical pane on the far right side of the screen. 

.. note::
  
  Integrations currently registered to the channel header will move to the Apps Bar automatically; however, we strongly encourage Mattermost integrators to update their integrations to provide the best user experience. See the `channel header plugin changes <https://forum.mattermost.com/t/channel-header-plugin-changes/13551>`__ user forum discussion for details on how to register integrations with the Apps Bar.

**True**: All integration icons in the channel header move to the Apps Bar with the exception of the calls beta feature.

**False**: All integration icons in the channel header display in the channel header.

+----------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableAppBar": false`` with options ``true`` and ``false``. |
+----------------------------------------------------------------------------------------------------------+

----

Experimental Bleve configuration settings
-----------------------------------------

.. include:: ../_static/badges/allplans-selfhosted.rst
  :start-after: :nosearch:

Access the following configuration settings in the System Console by going to **Experimental > Bleve**, or by editing the ``config.json`` file as described in the following tables:

Enable Bleve indexing
~~~~~~~~~~~~~~~~~~~~~

**True**: The indexing of new posts occurs automatically. Search queries will not use bleve search until `Enable Bleve for search queries <https://docs.mattermost.com/configure/configuration-settings.html#enable-bleve-for-search-queries>`__ is enabled.

**False**: The indexing of new posts does not occur automatically.

+------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableIndexing": false`` with options ``true`` and ``false``. |
+------------------------------------------------------------------------------------------------------------+

Index directory
~~~~~~~~~~~~~~~

Directory path to use for storing bleve indexes. 

.. tip::
   
   The bleve index directory path isn't required to exist within the ``mattermost`` directory. When it exists outside of the ``mattermost`` directory, no  additional steps are needed to preserve or reindex these files as part of a Mattermost upgrade. See our `Upgrading Mattermost Server <https://docs.mattermost.com/upgrade/upgrading-mattermost-server.html>`__ documentation for details. 

+-----------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"IndexDir": ""`` with string input.                           |
+-----------------------------------------------------------------------------------------------------------+

Bulk index now
~~~~~~~~~~~~~~

Select **Index Now** to index all users, channels, and posts in the database from oldest to newest. Bleve is available during indexing, but search results may be incomplete until the indexing job is complete.

You can configure the maximum time window used for a batch of posts being indexed. See the `Bulk Indexing Time Window Seconds <https://docs.mattermost.com/configure/configuration-settings.html#bulk-indexing-time-window-seconds>`__ documentation for details.

Purge indexes
~~~~~~~~~~~~~~

Select **Purge Index** to remove the contents of the Bleve index directory. Search results may be incomplete until a bulk index of the existing database is rebuilt.

Enable Bleve for search queries
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

**True**: Search queries will use bleve search.

**False**: Search queries will not use bleve search.

+--------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableSearching": false`` with options ``true`` and ``false``.  |
+--------------------------------------------------------------------------------------------------------------+

Enable Bleve for autocomplete queries
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

**True**: Autocomplete queries will use bleve search.

**False**: Autocomplete queries will not use bleve search.

+-----------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableAutocomplete": false`` with options ``true`` and ``false``.  |
+-----------------------------------------------------------------------------------------------------------------+

----

Experimental configuration settings for self-hosted deployments only
--------------------------------------------------------------------

.. include:: ../_static/badges/allplans-selfhosted.rst
  :start-after: :nosearch:

Access the following self-hosted configuration settings by editing the ``config.json`` file as described in the following tables. These configuration settings are not accessible through the System Console.

.. include:: common-config-settings-notation.rst
    :start-after: :nosearch:

Allowed themes
~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-pro-only.rst
  :start-after: :nosearch:

*Available in legacy Enterprise Edition E10 and E20*

This setting isn't available in the System Console and can only be set in ``config.json``.

Select the themes that can be chosen by users when ``EnableThemeSelection`` is set to ``true``. 

+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"AllowedThemes": []`` with string array input consisting of the options ``"default"``, ``"organization"``, ``"mattermostDark"``, and ``"windows10"``, such as ``["mattermostDark", "windows10"]``.     |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Maximum users for statistics
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-pro-only.rst
  :start-after: :nosearch:

*Available in legacy Enterprise Edition E10 and E20*

This setting isn't available in the System Console and can only be set in ``config.json``.

Sets the maximum number of users on the server before statistics for total posts, total hashtag posts, total file posts, posts per day, and active users with posts per day are disabled. 

This setting is used to maximize performance for large Enterprise deployments.

+---------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"MaxUsersForStatistics": 2500`` with numerical input. |
+---------------------------------------------------------------------------------------------------+

Latest Android version
~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

The latest version of the Android React Native app that is recommended for use. 

+----------------------------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"AndroidLatestVersion": ""`` with string input corresponding to a version string, such as ``"1.2.0"``. |
+----------------------------------------------------------------------------------------------------------------------------------------------------+

Minimum Android version
~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

The minimum version of the Android React Native app that is required to be used. 

+-------------------------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"AndroidMinVersion": ""`` with string input corresponding to a version string, such as ``"1.2.0"``. |
+-------------------------------------------------------------------------------------------------------------------------------------------------+

Latest iOS version
~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

The latest version of the iOS app that is recommended for use. 

+------------------------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"IosLatestVersion": ""`` with string input corresponding to a version string, such as ``"1.2.0"``. |
+------------------------------------------------------------------------------------------------------------------------------------------------+

Minimum iOS version
~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

The minimum version of the iOS React Native app that is required to be used. 

+---------------------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"IosMinVersion": ""`` with string input corresponding to a version string, such as ``"1.2.0"``. |
+---------------------------------------------------------------------------------------------------------------------------------------------+

Batch size
~~~~~~~~~~~

.. include:: ../_static/badges/ent-only.rst
  :start-after: :nosearch:

*Available in legacy Enterprise Edition E20*

This setting isn't available in the System Console and can only be set in ``config.json``.

Determines how many new posts are batched together to a compliance export file.

+----------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"BatchSize": 10000`` with numerical input. |
+----------------------------------------------------------------------------------------+

File Location
~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-only.rst
  :start-after: :nosearch:

*Available in legacy Enterprise Edition E20*

This setting isn't available in the System Console and can only be set in ``config.json``.

Set the file location of the compliance exports. By default, they are written to the ``exports`` subdirectory of the configured `Local Storage directory <https://docs.mattermost.com/configure/configuration-settings.html#local-storage-directory>`__.

+-------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"FileLocation": "export"`` with string input. |
+-------------------------------------------------------------------------------------------+

Push notification buffer
~~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

Used to control the buffer of outstanding Push Notification messages to be sent. If the number of messages exceeds that number, then the request making the Push Notification will be blocked until there's room. 

+---------------------------------------------------------------------------------------------------------------------------------------------+
| This feature’s ``config.json`` setting is ``"PushNotificationBuffer": 1000"`` with numerical input.                                         |
+---------------------------------------------------------------------------------------------------------------------------------------------+

Disable inactive server email notifications
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

This configuration setting disables the ability to send inactivity email notifications to Mattermost System Admins.

+-------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableInactivityEmail": true`` with options ``true`` and ``false``.  |
+-------------------------------------------------------------------------------------------------------------------+

File configuration options
~~~~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

Enable this setting to write audit files locally, specifying size, backup interval, compression, maximum age to manage file rotation, and timestamps. 

**True**: File output is enabled.

**False**: File output is disabled.

+---------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"FileEnabled": false`` with options ``true`` and ``false``. |
+---------------------------------------------------------------------------------------------------------+

File name
~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

This is the path to the output file location. 

+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"FileName": ""`` with string input consisting of a user-defined path (e.g. ``/var/log/mattermost_audit.log``).                                    |
+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

File max size MB
~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

This is the maximum size (measured in megabytes) that the file can grow before triggering rotation. The default setting is 100. 

+------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"FileMaxSizeMB": 100`` with numerical input. |
+------------------------------------------------------------------------------------------+

File max age days
~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

This is the maximum age in days a file can reach before triggering rotation. The default value is 0, indicating no limit on the age. 

+-----------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"FileMaxAgeDays": 0`` with numerical input. |
+-----------------------------------------------------------------------------------------+

File max backups
~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

This is the maximum number of rotated files kept; the oldest is deleted first. The default value is 0, indicating no limit on the number of backups. 

+-----------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"FileMaxBackups": 0`` with numerical input. |
+-----------------------------------------------------------------------------------------+

File compress
~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

When ``true``, rotated files are compressed using ``gzip``. 

+----------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"FileCompress": false`` with options ``true`` and ``false``. |
+----------------------------------------------------------------------------------------------------------+

File max queue size
~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

This setting determines how many audit records can be queued/buffered at any point in time when writing to a file. The default is 1000 records. 
This setting can be left as default unless you are seeing audit write failures in the server log and need to adjust the number accordingly.

+----------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"FileMaxQueueSize": 1000`` with numerical input. |
+----------------------------------------------------------------------------------------------+

Syslog configuration options
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

Enable this setting to write audit records to a local or remote syslog, specifying the IP, port, user-generated fields, and certificate settings. 

**True**: Syslog output is enabled.

**False**: Syslog output is disabled.

+-----------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"SysLogEnabled": false`` with options ``true`` and ``false``. |
+-----------------------------------------------------------------------------------------------------------+

Syslog IP
~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

The IP address or domain of the syslog server. Use ``localhost`` for local syslog. 

+-------------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"SysLogIP": "localhost"`` with string input consisting of an IP address or domain name. |
+-------------------------------------------------------------------------------------------------------------------------------------+

Syslog port
~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

The port that the syslog server is listening on. The default port is 6514. 

+------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"SysLogPort": 6514`` with numeric input consisting of a port number. |
+------------------------------------------------------------------------------------------------------------------+

Syslog tag
~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

The syslog metadata tag field.

+-------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"SysLogTag": ""`` with string input consisting of a user-defined tag field. |
+-------------------------------------------------------------------------------------------------------------------------+

Syslog cert
~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

This is the path to the syslog server certificate for TLS connections (``.crt`` or ``.pem``). 

+-----------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"SysLogCert": ""`` with string input consisting of the path to the certificate. |
+-----------------------------------------------------------------------------------------------------------------------------+

Syslog insecure
~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

This setting controls whether a client verifies the server's certificate chain and host name. If ``true``, TLS accepts any certificate presented by the server and any host name in that certificate. In this mode, TLS is susceptible to man-in-the-middle attacks. 

.. note:: 
   This should be used only for testing and not in a production environment.

+------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"SysLogInsecure": false`` with options ``true`` and ``false``. |
+------------------------------------------------------------------------------------------------------------+

Syslog max queue size
~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

This setting determines how many audit records can be queued/buffered at any point in time when writing to syslog. The default is 1000 records. 
This setting can be left as default unless you are seeing audit write failures in the server log and need to adjust the number accordingly.

+------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"SysLogMaxQueueSize": 1000`` with numerical input. |
+------------------------------------------------------------------------------------------------+

Restrict system admin
~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

**True**: Restricts the System Admin from viewing and modifying a subset of server configuration settings from the System Console. Not recommended for use in on-prem installations. This is intended to support Mattermost Private Cloud in giving the System Admin role to users but restricting certain actions only for Cloud Admins.

**False**: No restrictions are applied to the System Admin role.

+-------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"RestrictSystemAdmin": "false"`` with options ``true`` and ``false``. |
+-------------------------------------------------------------------------------------------------------------------+

Remote clusters
~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-only.rst
  :start-after: :nosearch:

*Available in legacy Enterprise Edition E20*

This setting isn't available in the System Console and can only be set in ``config.json``.

Enable this setting to add, remove, and view remote clusters for shared channels. 

**True**: System Admins can manage remote clusters using the System Console.

**False**: Remote cluster management is disabled.

+------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"RemoteClusters": false`` with options ``true`` and ``false``. |
+------------------------------------------------------------------------------------------------------------+

Enable client-side certification
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-only.rst
  :start-after: :nosearch:

*Available in legacy Enterprise Edition E20*

**True**: Enables client-side certification for your Mattermost server. See `the documentation <https://docs.mattermost.com/onboard/certificate-based-authentication.html>`__ to learn more.

**False**: Client-side certification is disabled.

+------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"ClientSideCertEnable": false`` with options ``true`` and ``false``. |
+------------------------------------------------------------------------------------------------------------------+

Client-side certification login method
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-only.rst
  :start-after: :nosearch:

*Available in legacy Enterprise Edition E20*

Used in combination with the ``ClientSideCertEnable`` configuration setting.

**Primary**: After the client side certificate is verified, user's email is retrieved from the certificate and is used to log in without a password.

**Secondary**: After the client side certificate is verified, user's email is retrieved from the certificate and matched against the one supplied by the user. If they match, the user logs in with regular email/password credentials.

+----------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"ClientSideCertCheck": "secondary"`` with options ``"primary"`` and ``"secondary"``. |
+----------------------------------------------------------------------------------------------------------------------------------+

Export settings default directory
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

The directory where the exported files are stored. The path is relative to the ``FileSettings`` directory. By default, exports are stored under ``./data/export``.

+---------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting under the ``ExportSettings`` section is ``Directory: ./export`` with string input. |
+---------------------------------------------------------------------------------------------------------------------------+

Export settings default retention days
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

The number of days to retain the exported files before deleting them.

+----------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting under the ``ExportSettings`` section is ``RetentionDays: 30`` with numerical input. |
+----------------------------------------------------------------------------------------------------------------------------+

Maximum image resolution
~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

Maximum image resolution size for message attachments in pixels. 

+--------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"MaxImageResolution": 33177600`` with numerical input.     |
+--------------------------------------------------------------------------------------------------------+

Maximum image decoder concurrency
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

Indicates how many images can be decoded concurrently at once. The default value of ``-1`` configures Mattermost to automatically use the number of CPUs present.

.. note::

  This configuration setting affects the total memory consumption of the server. The maximum memory of a single image is dictated by ``MaxImageResolution * 24 bytes`` Therefore, a good rule of thumb to follow is that ``MaxImageResolution* MaxImageDecoderConcurrency * 24`` should be less than the allocated memory for image decoding.

+--------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"MaxImageDecoderConcurrency": "-1"`` with numerical input. |
+--------------------------------------------------------------------------------------------------------+

Initial font
~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

Font used in auto-generated profile pics with colored backgrounds.

+-----------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"InitialFont": "luximbi.ttf"`` with string input. |
+-----------------------------------------------------------------------------------------------+

Amazon S3 signature v2
~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

By default, Mattermost uses Signature V4 to sign API calls to AWS, but under some circumstances, V2 is required. For more information about when to use V2, see https://docs.aws.amazon.com/general/latest/gr/signature-version-2.html.

**True**: Use Signature Version 2 Signing Process.

**False**: Use Signature Version 4 Signing Process.

+------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"AmazonS3SignV2": false`` with options ``true`` and ``false``. |
+------------------------------------------------------------------------------------------------------------+

Amazon S3 path
~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

Allows using the same S3 bucket for multiple deployments.

+------------------------------------------------------------------------------------------------------------+
| This feature’s ``config.json`` setting is ``"AmazonS3PathPrefix: ""`` with string input.                   |
+------------------------------------------------------------------------------------------------------------+

GitLab scope
~~~~~~~~~~~~~~

*Not available in Cloud Starter*

This setting isn't available in the System Console and can only be set in ``config.json``.

Standard setting for OAuth to determine the scope of information shared with OAuth client. Not currently supported by GitLab OAuth.

+------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"Scope": ""`` with string input. |
+------------------------------------------------------------------------------+

Global relay SMTP server timeout
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-only.rst
  :start-after: :nosearch:

*Available as an add-on to legacy Enterprise Edition E20*

This setting isn't available in the System Console and can only be set in ``config.json``.

The number of seconds that can elapse before the connection attempt to the SMTP server is abandoned. The default value is 1800 seconds. This setting is currently not available in the System Console and can only be set in ``config.json``.

+-----------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"GlobalRelaySettings.SMTPServerTimeout": "1800"`` with numerical input.   |
+-----------------------------------------------------------------------------------------------------------------------+

Google scope
~~~~~~~~~~~~

.. include:: ../_static/badges/ent-pro-only.rst
  :start-after: :nosearch:

*Available in legacy Enterprise Edition E20*

This setting isn't available in the System Console and can only be set in ``config.json``.

Standard setting for OAuth to determine the scope of information shared with OAuth client. Recommended setting is ``profile email``.

+-------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"Scope": "profile email"`` with string input. |
+-------------------------------------------------------------------------------------------+

Import settings default directory
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

The directory where the imported files are stored. The path is relative to the ``FileSettings`` directory. By default, imports are stored under ``./data/import``.

+---------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting under the ``ImportSettings`` section is ``Directory: ./import`` with string input. |
+---------------------------------------------------------------------------------------------------------------------------+

Import settings default retention days
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

The number of days to retain the imported files before deleting them.

+----------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting under the ``ImportSettings`` section is ``RetentionDays: 30`` with numerical input. |
+----------------------------------------------------------------------------------------------------------------------------+

Export from timestamp
~~~~~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-only.rst
  :start-after: :nosearch:

*Available in legacy Enterprise Edition E20*

This setting isn't available in the System Console and can only be set in ``config.json``.

Set the Unix timestamp (seconds since epoch, UTC) to export data from. 

+----------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"ExportFromTimestamp": 0`` with numerical input. |
+----------------------------------------------------------------------------------------------+

Block profile rate
~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``. Changes to this setting require a server restart before taking effect.

Value that controls the `fraction of goroutine blocking events reported in the blocking profile <https://golang.org/pkg/runtime/#SetBlockProfileRate>`__.

The profiler aims to sample an average of one blocking event per rate nanoseconds spent blocked.

To include every blocking event in the profile, set the rate to ``1``. To turn off profiling entirely, set the rate to ``0``.

+---------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"BlockProfileRate": 0`` with options ``0`` and ``1``. |
+---------------------------------------------------------------------------------------------------+

App custom URL schemes
~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

Define valid custom URL schemes for redirect links provided by custom-built mobile Mattermost apps. This ensures users are redirected to the custom-built mobile app and not Mattermost's mobile client. 

When configured, after OAuth or SAML user authentication is complete, custom URL schemes sent by mobile clients are validated to ensure they don't include default schemes such as ``http`` or ``https``. Mobile users are then redirected back to the mobile app using the custom scheme URL provided by the mobile client. We recommend that you update your mobile client values as well with valid custom URL schemes.

+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"NativeAppSettings.AppCustomURLSchemes"`` with an array of strings as input. For example: ``[custom-app://, some-app://]``.                    |
+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Office 365 Scope
~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-pro-only.rst
  :start-after: :nosearch:

*Available in legacy Enterprise Edition E20*

This setting isn't available in the System Console and can only be set in ``config.json``.

Standard setting for OAuth to determine the scope of information shared with OAuth client. Recommended setting is ``User.Read``.

+---------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"Scope": "User.Read"`` with string input. |
+---------------------------------------------------------------------------------------+

Enable plugin uploads
~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

**True**: Enables plugin uploads by System Admins at **Plugins > Management**. If you do not plan to upload a plugin, set to ``false`` to control which plugins are installed on your server. See `documentation <https://developers.mattermost.com/integrate/admin-guide/admin-plugins-beta/>`__ to learn more.

**False**: Disables plugin uploads on your Mattermost server.

+-----------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableUploads": false`` with options ``true`` and ``false``. |
+-----------------------------------------------------------------------------------------------------------+

Allow insecure download URL
~~~~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

**True**: Enables downloading and installing a plugin from a remote URL.

**False**: Disables downloading and installing a plugin from a remote URL.

+-----------------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"AllowInsecureDownloadUrl": false`` with options ``true`` and ``false``.                    |
+-----------------------------------------------------------------------------------------------------------------------------------------+

Enable plugin health check
~~~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

**True**: Enables plugin health check to ensure all plugins are periodically monitored, and restarted or deactivated based on their health status. The health check runs every 30 seconds. If the plugin is detected to fail 3 times within an hour, the Mattermost server attempts to restart it. If the restart fails 3 successive times, it's automatically disabled.

**False**: Disables plugin health check on your Mattermost server.

+--------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableHealthCheck": true`` with options ``true`` and ``false``. |
+--------------------------------------------------------------------------------------------------------------+

Plugin directory
~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

The location of the plugin files. If blank, they are stored in the ``./plugins`` directory. The path that you set must exist and Mattermost must have write permissions in it. 

+-----------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"Directory": "./plugins"`` with string input.                       |
+-----------------------------------------------------------------------------------------------------------------+

Client plugin directory
~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

The location of client plugin files. If blank, they are stored in the ``./client/plugins`` directory. The path that you set must exist and Mattermost must have write permissions in it. 

+-----------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"ClientDirectory": "./client/plugins"`` with string input.          |
+-----------------------------------------------------------------------------------------------------------------+

Scoping IDP provider ID
~~~~~~~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-pro-only.rst
  :start-after: :nosearch:

*Available in legacy Enterprise Edition E20*

This setting isn't available in the System Console and can only be set in ``config.json``.

Allows an authenticated user to skip the initial login page of their federated Azure AD server, and only require a password to log in.

+---------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"ScopingIDPProviderId": ""`` with string input. |
+---------------------------------------------------------------------------------------------+

Scoping IDP provider name
~~~~~~~~~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-pro-only.rst
  :start-after: :nosearch:

*Available in legacy Enterprise Edition E20*

This setting isn't available in the System Console and can only be set in ``config.json``.

Adds the name associated with a user's Scoping Identity Provider ID.

+---------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"ScopingIDPName": ""`` with string input. |
+---------------------------------------------------------------------------------------+

Group unread channels
~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

This setting applies to the new sidebar only. You must disable the `Enable Legacy Sidebar <https://docs.mattermost.com/configure/configuration-settings.html#enable-legacy-sidebar>`__ configuration setting to see and enable this functionality in the System Console. 

**Default Off**: Disables the unread channels sidebar section for all users by default. Users can enable it in **Settings > Sidebar > Group unread channels separately**.

**Default On**: Enables the unread channels sidebar section for all users by default. Users can disable it in **Settings > Sidebar > Group unread channels separately**. 

+-----------------------------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"ExperimentalGroupUnreadChannels": "default_off"`` with options ``"default_off"`` and ``"default_on"``. |
+-----------------------------------------------------------------------------------------------------------------------------------------------------+

Strict CSRF token enforcement
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

**True**: Enables CSRF protection tokens for additional hardening compared to the currently used custom header. When the user logs in, an additional cookie is created with the CSRF token contained.

**False**: Disables CSRF protection tokens.

+-------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"ExperimentalStrictCSRFEnforcement": false`` with options ``true`` and ``false``. |
+-------------------------------------------------------------------------------------------------------------------------------+

Custom user groups
~~~~~~~~~~~~~~~~~~~

.. include:: ../_static/badges/ent-pro-only.rst
  :start-after: :nosearch:

This setting isn't available in the System Console and can only be set in ``config.json``.

This configuration setting controls the ability for users to create custom user groups. This configuration setting is enabled by default for both self-hosted and Cloud deployments, but can only be disabled in self-hosted deployments.

+----------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableCustomGroups": true`` with options ``true`` and ``false``.  |
+----------------------------------------------------------------------------------------------------------------+

Developer flags
~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

This configuration setting specifies a list of strings where each string is a flag used to set the content security policy (CSP) for the Mattermost Web App. Each flag must be in the format ``flag=true`` (e.g. ``unsafe-eval=true,unsafe-inline=true``). Not recommended for production environments.

The following values are currently supported:

- ``unsafe-eval``: Adds the ``unsafe-eval`` CSP directive to the root webapp, allowing increased debugging in developer environments.
- ``unsafe-inline``: Adds the ``unsafe-inline`` CSP directive to the root webapp, allowing increased debugging in developer environments.

This configuration setting is disabled by default and requires `developer mode <https://docs.mattermost.com/configure/configuration-settings.html#enable-developer-mode>`__ to be enabled. 

+----------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"DeveloperFlags": ""`` with string input.  |
+----------------------------------------------------------------------------------------+

Enable post search
~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

If this setting is enabled, users can search messages. Disabling search can result in a performance increase, but users get an error message when they attempt to use the search box.

+-------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnablePostSearch": true`` with options ``true`` and ``false``. |
+-------------------------------------------------------------------------------------------------------------+

Enable file search
~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

This configuration setting enables users to search documents attached to messages by filename. To enable users to search documents by their content, you must also enable the ``ExtractContent`` configuration setting. See our `Enable Document Search by Content <https://docs.mattermost.com/configure/configuration-settings.html#enable-document-search-by-content>`__ documentation for details. Document content search is available in Mattermost Server from v5.35, with mobile support coming soon. 

**True**: Supported document types are searchable by their filename. 

**False**: File-based searches are disabled.

+-------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableFileSearch": true`` with options ``true`` and ``false``. |
+-------------------------------------------------------------------------------------------------------------+

Enable user status updates
~~~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

Turn status updates off to improve performance. When status updates are off, users appear online only for brief periods when posting a message, and only to members of the channel in which the message is posted.

+---------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableUserStatuses": true`` with options ``true`` and ``false``. |
+---------------------------------------------------------------------------------------------------------------+

Websocket secure port
~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``. Changes to this setting require a server restart before taking effect.

(Optional) This setting defines the port on which the secured WebSocket will listen using the ``wss`` protocol. Defaults to ``443``. When the client attempts to make a WebSocket connection it first checks to see if the page is loaded with HTTPS. If so, it will use the secure WebSocket connection. If not, it will use the unsecure WebSocket connection. IT IS HIGHLY RECOMMENDED PRODUCTION DEPLOYMENTS ONLY OPERATE UNDER HTTPS AND WSS.

+------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"WebsocketSecurePort": 443`` with numerical input. |
+------------------------------------------------------------------------------------------------+

Websocket port
~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``. Changes to this setting require a server restart before taking effect.

(Optional) This setting defines the port on which the unsecured WebSocket will listen using the ``ws`` protocol. Defaults to ``80``. When the client attempts to make a WebSocket connection it first checks to see if the page is loaded with HTTPS. If so, it will use the secure WebSocket connection. If not, it will use the unsecure WebSocket connection. IT IS HIGHLY RECOMMENDED PRODUCTION DEPLOYMENTS ONLY OPERATE UNDER HTTPS AND WSS.

+----------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``WebsocketPort": 80`` with numerical input. |
+----------------------------------------------------------------------------------------+

Enable API team deletion
~~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

**True**: The ``api/v4/teams/{teamid}?permanent=true`` API endpoint can be called by Team and System Admins to permanently delete a team.

**False**: The API endpoint cannot be called. Note that ``api/v4/teams/{teamid}`` can still be used to soft delete a team.

+-------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableAPITeamDeletion": false`` with options ``true`` and ``false``. |
+-------------------------------------------------------------------------------------------------------------------+

Enable API user deletion
~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

**True**: The ``api/v4/users/{userid}?permanent=true`` API endpoint can be called by System Admins, or users with appropriate permissions, to permanently delete a user.

**False**: The API endpoint cannot be called. Note that ``api/v4/users/{userid}`` can still be used to soft delete a user.

+-------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableAPIUserDeletion": false`` with options ``true`` and ``false``. |
+-------------------------------------------------------------------------------------------------------------------+

Enable API channel deletion
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

**True**: The ``api/v4/channels/{channelid}?permanent=true`` API endpoint can be called by System Admins, or users with appropriate permissions, to permanently delete a channel.

**False**: The API endpoint cannot be called. Note that ``api/v4/channels/{channelid}`` can still be used to soft delete a channel.

+----------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableAPIChannelDeletion": false`` with options ``true`` and ``false``. |
+----------------------------------------------------------------------------------------------------------------------+

Enable OpenTracing
~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

**True**: A Jaeger client is instantiated and is used to trace each HTTP request as it goes through App and Store layers. Context is added to App and Store and is passed down the layer chain to create OpenTracing 'spans'.

By default, in order to avoid leaking sensitive information, no method parameters are reported to OpenTracing. Only the name of the method is reported.

**False**: OpenTracing is not enabled.

+---------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableOpenTracing": false`` with options ``true`` and ``false``. |
+---------------------------------------------------------------------------------------------------------------+

Enable local mode for mmctl
~~~~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

**True**: Enables local mode for mmctl.

**False**: Prevents local mode for mmctl.

+-------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"EnableLocalMode": false`` with options ``true`` and ``false``. |
+-------------------------------------------------------------------------------------------------------------+

.. tip::

  When trying to use local mode with mmctl, an error like ``socket file "/var/tmp/mattermost_local.socket" doesn't exists, please check the server configuration for local mode``, can be resolved by setting this configuration setting to ``true``.

Enable local mode socket location
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

The path for the socket that the server will create for mmctl to connect and communicate through local mode. If the default value for this key is changed, you will need to point mmctl to the new socket path when in local mode, using the ``--local-socket-path /new/path/to/socket`` flag in addition to the ``--local`` flag.

If nothing is specified, the default path that both the server and mmctl assumes is ``/var/tmp/mattermost_local.socket``.

+--------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"LocalModeSocketLocation": "/var/tmp/mattermost_local.socket"`` with string input. |
+--------------------------------------------------------------------------------------------------------------------------------+

Default channels
~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

Default channels every user is added to automatically after joining a new team. Only applies to Public channels, but affects all teams on the server. 

When not set, every user is added to the ``off-topic`` and ``town-square`` channels by default.

.. note::

   Even if ``town-square`` is not listed, every user is added to that channel after joining a new team.

+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"ExperimentalDefaultChannels": []`` with string array input consisting of channel names, such as ``["announcement", "developers"]``. |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

----

Experimental job configuration settings
---------------------------------------

.. include:: ../_static/badges/allplans-selfhosted.rst
  :start-after: :nosearch:

Settings to configure how Mattermost schedules and completes periodic tasks such as the deletion of old posts with Data Retention enabled or indexing posts with Elasticsearch. These settings control which Mattermost servers are designated as a Scheduler, a server that queues the tasks at the correct times, and as a Worker, a server that completes the given tasks.

When running Mattermost on a single machine, both ``RunJobs`` and ``RunScheduler`` should be enabled. Without both of these enabled, Mattermost will not function properly.

When running Mattermost in High Availability mode, ``RunJobs`` should be enabled on one or more servers while ``RunScheduler`` should be enabled on all servers under normal circumstances. A High Availability cluster will have one Scheduler and one or more Workers. See the below sections for more information.

Run jobs
~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

Set whether or not this Mattermost server will handle tasks created by the Scheduler. When running Mattermost on a single machine, this setting should always be enabled.

When running Mattermost in `High Availablity mode <https://docs.mattermost.com/scale/high-availability-cluster.html>`__, one or more servers should have this setting enabled. We recommend that your High Availability cluster has one or more dedicated Workers with this setting enabled while the remaining Mattermost app servers have it disabled.

+------------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"RunJobs": true`` with options ``true`` and ``false``.                                 |
+------------------------------------------------------------------------------------------------------------------------------------+

Run scheduler
~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

Set whether or not this Mattermost server will schedule tasks that will be completed by a Worker. When running Mattermost on a single machine, this setting should always be enabled.

When running Mattermost in `High Availablity mode <https://docs.mattermost.com/scale/high-availability-cluster.html>`__, this setting should always be enabled. In a High Availability cluster, exactly one of the servers will be designated as the Scheduler at a time to ensure that duplicate tasks aren't created. See `High Availability documentation <https://docs.mattermost.com/scale/high-availability-cluster.html>`__ for more details.

.. warning::

   We strongly recommend that you not change this setting from the default setting of ``true`` as this prevents the ``ClusterLeader`` from being able to run the scheduler. As a result, recurring jobs such as LDAP sync, Compliance Export, and data retention will no longer be scheduled. In previous Mattermost Server versions, and this documentation, the instructions stated to run the Job Server with ``RunScheduler: false``. The cluster design has evolved and this is no longer the case.

+-----------------------------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"RunScheduler": true`` with options ``true`` and ``false``.                                 |
+-----------------------------------------------------------------------------------------------------------------------------------------+

Clean Up old database jobs
~~~~~~~~~~~~~~~~~~~~~~~~~~

This setting isn't available in the System Console and can only be set in ``config.json``.

Defines the threshold in hours beyond which older completed database jobs are removed. This setting applies to both MySQL and PostgreSQL databases, is disabled by default, and must be set to a value greater than or equal to ``0`` to be enabled.

+--------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"JobSettings.CleanupJobsThresholdDays": -1`` with numerical input.     |
+--------------------------------------------------------------------------------------------------------------------+

Clean up outdated database entries
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This setting only applies to configuration in the database. It isn't available in the System Console and can be set via mmctl or changed in the database.

Defines the threshold in days beyond which outdated configurations are removed from the database. This setting applies to both MySQL and PostgreSQL databases.

+--------------------------------------------------------------------------------------------------------------------+
| This feature's ``config.json`` setting is ``"JobSettings.CleanupConfigThresholdDays": 30`` with numerical input.   |
+--------------------------------------------------------------------------------------------------------------------+