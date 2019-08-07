# ansible-squad

Install OWI Squad Server on Windows or Linux. Additionally configure the server, and install mods.

## Example playbook

```yaml
---
- name: Provision a server as a Squad server
  hosts: elrond
  gather_facts: false
  vars:
    - vars/main.yml
  roles:
    - squad
```


`vars/main.yml`
```yaml
---
squad_server_os: windows # Can be either 'windows' or 'linux'. Windows is necessary for certain mods.

squad_server_mods:
  - 1205163003 # Helicopter https://steamcommunity.com/sharedfiles/filedetails/?id=1205163003
  - 1313956617 # Karkand    https://steamcommunity.com/sharedfiles/filedetails/?id=1313956617

squad_server_admins:
  - { name: "Crispy", admin_group: "SuperAdmin", steam_id: "76561197996838808" }
  - { name: "Matt", admin_group: "SuperAdmin", steam_id: "76561198019050501" }

squad_server_bans:
  - { name: "Thanos", reason: "Permanent ban for cheating", unban_timestamp: "0", steam_id: "76561198039509812" }
  - { name: "Loki", reason: "Team killing", unban_timestamp: "1454455855", steam_id: "7862895148978485" }

squad_server_maps:
  - Strike_at_Karkand_V15_DAY_AAS_v2
  - Strike_at_Karkand_V15_Morning_AAS_v2
  - Strike_at_Karkand_V15_DAY_AAS_v1

squad_server_messsages:
  - Thank you for playing on our server!
  - Please apologize in ALL chat for any teamkills
  - Check out KorruptedGamers.com

squad_server_motd:
  - Server brought to you by KorruptedGamers.com

squad_server_name: "[KG] 24/7 Karkand"
squad_server_capacity: 24 # 12, 24, 48, or 80.
squad_server_enforce_team_balance: false
squad_server_message_interval: 300
squad_server_vehicle_claiming_disabled: true
squad_server_vehicle_kit_requirement_disabled: true
squad_server_should_advertise: true
squad_server_allow_team_changes: true
squad_server_num_reserved_slots: 0
squad_server_num_players_diff_for_team_changes: 3
squad_server_prevent_team_change_if_unbalanced: true
squad_server_rejoin_squad_delay_after_kick: 180
squad_server_auto_tk_ban_time: 1209600
squad_server_tk_auto_kick_enabled: true
squad_server_watchdog_port: 80
squad_server_query_port: 27165
squad_server_port: 7787
```
