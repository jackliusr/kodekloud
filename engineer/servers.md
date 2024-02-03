```bash
java -jar jenkins-cli.jar -s https://8080-port-./ -webSocket install-plugin SOURCE ... [-deploy] [-name VAL] [-restart]

java -jar jenkins-cli.jar -s <JENKINS_URL> create-credentials-by-xml  system::system::jenkins _ < credential-name.xml

# can we run docker at jenkins server?
```

<table>
    <thead>
        <tr>
            <th style="text-align: left"><strong>Server Name</strong></th>
            <th style="text-align: left"><strong>IP</strong></th>
            <th style="text-align: left"><strong>Hostname</strong></th>
            <th style="text-align: left"><strong>User</strong></th>
            <th style="text-align: left"><strong>Password</strong></th>
            <th style="text-align: left"><strong>Purpose</strong></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="text-align: left">stapp01</td>
            <td style="text-align: left">172.16.238.10</td>
            <td style="text-align: left">stapp01.stratos.xfusioncorp.com</td>
            <td style="text-align: left">tony</td>
            <td style="text-align: left">Ir0nM@n</td>
            <td style="text-align: left">Nautilus App 1</td>
        </tr>
        <tr>
            <td style="text-align: left">stapp02</td>
            <td style="text-align: left">172.16.238.11</td>
            <td style="text-align: left">stapp02.stratos.xfusioncorp.com</td>
            <td style="text-align: left">steve</td>
            <td style="text-align: left">Am3ric@</td>
            <td style="text-align: left">Nautilus App 2</td>
        </tr>
        <tr>
            <td style="text-align: left">stapp03</td>
            <td style="text-align: left">172.16.238.12</td>
            <td style="text-align: left">stapp03.stratos.xfusioncorp.com</td>
            <td style="text-align: left">banner</td>
            <td style="text-align: left">BigGr33n</td>
            <td style="text-align: left">Nautilus App 3</td>
        </tr>
        <tr>
            <td style="text-align: left">stlb01</td>
            <td style="text-align: left">172.16.238.14</td>
            <td style="text-align: left">stlb01.stratos.xfusioncorp.com</td>
            <td style="text-align: left">loki</td>
            <td style="text-align: left">Mischi3f</td>
            <td style="text-align: left">Nautilus HTTP LBR</td>
        </tr>
        <tr>
            <td style="text-align: left">stdb01</td>
            <td style="text-align: left">172.16.239.10</td>
            <td style="text-align: left">stdb01.stratos.xfusioncorp.com</td>
            <td style="text-align: left">peter</td>
            <td style="text-align: left">Sp!dy</td>
            <td style="text-align: left">Nautilus DB Server</td>
        </tr>
        <tr>
            <td style="text-align: left">ststor01</td>
            <td style="text-align: left">172.16.238.15</td>
            <td style="text-align: left">ststor01.stratos.xfusioncorp.com</td>
            <td style="text-align: left">natasha</td>
            <td style="text-align: left">Bl@kW</td>
            <td style="text-align: left">Nautilus Storage Server</td>
        </tr>
        <tr>
            <td style="text-align: left">stbkp01</td>
            <td style="text-align: left">172.16.238.16</td>
            <td style="text-align: left">stbkp01.stratos.xfusioncorp.com</td>
            <td style="text-align: left">clint</td>
            <td style="text-align: left">H@wk3y3</td>
            <td style="text-align: left">Nautilus Backup Server</td>
        </tr>
        <tr>
            <td style="text-align: left">stmail01</td>
            <td style="text-align: left">172.16.238.17</td>
            <td style="text-align: left">stmail01.stratos.xfusioncorp.com</td>
            <td style="text-align: left">groot</td>
            <td style="text-align: left">Gr00T123</td>
            <td style="text-align: left">Nautilus Mail Server</td>
        </tr>
        <tr>
            <td style="text-align: left">jump_host</td>
            <td style="text-align: left">Dynamic</td>
            <td style="text-align: left">jump_host.stratos.xfusioncorp.com</td>
            <td style="text-align: left">thor</td>
            <td style="text-align: left">mjolnir123</td>
            <td style="text-align: left">Jump Server to Access Stork DC</td>
        </tr>
        <tr>
            <td style="text-align: left">jenkins</td>
            <td style="text-align: left">172.16.238.19</td>
            <td style="text-align: left">jenkins.stratos.xfusioncorp.com</td>
            <td style="text-align: left">jenkins</td>
            <td style="text-align: left">j@rv!s</td>
            <td style="text-align: left">Jenkins Server for CI/CD</td>
        </tr>
    </tbody>
</table>
