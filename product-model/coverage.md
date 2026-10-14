---
scope: The core gallery extensions and the approval, ratings, favorites, user-class and user-options extensions of the web interface.
method: Static inspection of source, themes and tests at the pinned commit; nothing was executed.
covered:
- description: Accounts, sign-in, sign-up, profiles and account operations.
  paths:
  - ext/user/
  - core/User/
  - ext/user_config/
  - ext/user_config_editor/
- description: 'Posts: upload, listing and search, viewing, deletion and post information editing.'
  paths:
  - ext/upload/
  - ext/index/
  - ext/view/
  - ext/image/
  - core/ImageBoard/
  - core/Search/
  - core/Extension/DataHandlerExtension.php
  - ext/post_tags/
  - ext/post_source/
  - ext/post_owner/
  - ext/post_lock/
  - ext/download/
- description: Tags, the tag map and tag aliases.
  paths:
  - ext/tag_map/
  - ext/tag_list/
  - ext/alias_editor/
- description: Comments.
  paths:
  - ext/comment/
- description: Approval queue, ratings and favorites extensions.
  paths:
  - ext/approval/
  - ext/rating/
  - ext/favorites/
- description: Board Admin, Board Config and the Extension Manager.
  paths:
  - ext/admin/
  - ext/setup/
  - ext/ext_manager/
  - core/Config/
- description: User classes from defaults, the configuration file and the Permission Manager.
  paths:
  - ext/perm_manager/
  - ext/user_class_file/
exclusions:
- description: Rendering, themes, static assets and page framework.
  paths:
  - themes/
  - ext/static_files/
  - core/Page/
  - ext/four_oh_four/
  - ext/robots_txt/
- description: Media handlers, MIME detection and thumbnail generation internals.
  paths:
  - ext/handle_image/
  - ext/media/
  - ext/mime/
  - core/Media/
- description: Database, cache, network and utility plumbing, upgrades and installer.
  paths:
  - core/Database/
  - core/Cache/
  - core/Network/
  - core/Util/
  - core/Events/
  - core/Exceptions/
  - ext/upgrade/
  - ext/system/
  - ext/et/
  - index.php
- description: Logging, metrics and tracing outputs.
  paths:
  - ext/log_cli/
  - ext/log_console/
  - ext/log_db/
  - ext/log_logstash/
  - ext/log_net/
  - ext/log_otlp/
  - ext/metrics_otlp/
  - ext/metrics_statsd/
  - ext/trace_otlp/
  - ext/otlp_common/
- description: Tests, CI, containers and developer tooling.
  paths:
  - tests/
  - .github/
  - .docker/
  - .devcontainer/
  - core/Testing/
unmapped:
- description: Help pages and extension documentation pages.
  paths:
  - ext/help_pages/
- description: Sign-up redirect to the new member's profile in the user page code, a journey left out because the person signs in partway.
  paths:
  - ext/user/main.php
- description: Operator command line commands registered by core extensions.
  paths:
  - core/Util/CliApp.php
- description: 'Machine APIs: GraphQL, the booru-compatible APIs and API keys.'
  paths:
  - ext/graphql/
  - ext/danbooru_api/
  - ext/ouroboros_api/
  - ext/user_api_keys/
- description: Bulk actions on search results and bulk import.
  paths:
  - ext/bulk_actions/
  - ext/bulk_add/
  - ext/bulk_add_csv/
  - ext/bulk_download/
  - ext/cron_uploader/
- description: IP bans, word and tag filters, reports and other moderation extensions.
  paths:
  - ext/ipban/
  - ext/ban_words/
  - ext/image_hash_ban/
  - ext/report_image/
  - ext/trash/
  - ext/private_image/
  - ext/filter/
  - ext/tombstones/
- description: 'Community extensions: pools, notes, forum, private messages, wiki, blotter, artists, numeric score and relationships.'
  paths:
  - ext/pools/
  - ext/notes/
  - ext/forum/
  - ext/pm/
  - ext/wiki/
  - ext/blotter/
  - ext/artists/
  - ext/numeric_score/
  - ext/relationships/
- description: Other optional metadata, media and presentation extensions.
  paths:
  - ext/
limitations: []
---

# Coverage
