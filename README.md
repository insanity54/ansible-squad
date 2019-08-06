# ansible-squad

Install OWI Squad Server on Windows or Linux. Additionally configure the server, and install mods.

## Requirements

The target machine needs Chocolatey (if windows) and steamcmd. Due to how conditional role dependencies work ([don't work?](https://github.com/ansible/ansible/issues/40890)) in ansible, you must handle this yourself in the playbook which uses this role. Use galaxy roles `deekayen.chocolatey` and `siw36.ansible_steamcmd`.

Example `requirements.yml`--

```
---

- src: insanity54.ansible_squad
  name: squad

- src: deekayen.chocolatey
  name: chocolatey

- src: siw36.ansible_steamcmd
  name: steamcmd
```

## Windows notes

Because of licensing issues, the user must spin up their own Windows instance configured with WinRM before this playbook will run against it. See https://docs.ansible.com/ansible/latest/user_guide/windows_winrm.html#what-is-winrm
