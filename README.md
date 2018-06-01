## ElastAlert configuring


## Installation

1. Install ElastAlert into Python 2.7:
    ```bash
    pip install elastalert
    ```
1. Create dirs for configs:
    ```bash
    mkdir -p /etc/elastalert/rules
    ```
1. Place [elastalert.yml](elastalert.yml) into `/etc/elastalert`
1. Place [elastalert.service](elastalert.service) into `/lib/systemd/system/`.
1. Create indices into ElasticSearch:
    ```bash
    elastalert-create-index --config /etc/elastalert/elastalert.yml
    ```
1. Create some rules.
1. Test rules:
    ```bash
    elastalert-test-rule --config /etc/elastalert/elastalert.yml /etc/elastalert/rules/*.yml
    ```
1. Run service:
    ```bash
    systemctl daemon-reload                 # update configs
    systemctl enable elastalert.service     # auto run on startup
    systemctl start elastalert.service      # run
    systemctl status elastalert.service     # check status
    ```

## References

1. [Rules examples](https://github.com/Yelp/elastalert/tree/master/example_rules)
1. [Documentation](https://elastalert.readthedocs.io/en/latest/)
1. [Daemonizing](https://github.com/Yelp/elastalert/issues/194)
