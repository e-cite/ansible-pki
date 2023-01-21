# Ansible Rolle "PKI"

Rolle zur Verwaltung einer PKI mit folgenden Funktionen:
- Deployment von Root-CA-Zertifikaten
- Deployment von Zertifikaten

## Anforderungen

keine

## Variablen

- `pki__root_ca_certificates`: (*Optional, default auf undefined*)

  Liste mit Root-CA Zertifikaten, die deployed werden sollen.
  ~~~yaml
  # Beispiel:
  pki__root_ca_certificates:
    - name: RootCA Name 2023-1
      file: rootca_name_2023-1.crt
      certificate: |
        -----BEGIN CERTIFICATE-----
      ...
  ~~~
- `pki__certificates`: (*Optional, default auf undefined*)

  Liste mit Zertifikaten, die deployed werden sollen.
  ~~~yaml
  # Beispiel:
  pki__certificates:
  - name: host.example.com.2023
    file: /etc/ssl/certs/host.example.com.2023.pem
    certificate: |
      -----BEGIN CERTIFICATE-----
      ...
  ~~~

## Abhängigkeiten

keine

## Beispiel

    - hosts: all
      roles:
        - pki

## Lizenz

MIT
