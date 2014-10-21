bmm
===

#B Micro Messaging

bmm is a small UDP based messaging protocoll.


## Message-parts
### Header
<table id="header">
  <tr>
    <th colspan="3"><center>1 byte</center></th>
    <th><center>2 byte</center></th>
    <th><center>3 byte</center></th>
  </tr>
  <tr>
    <th colspan="5"><center>bits</center></th>
  </tr>
  <tr>
    <td>1 2 3 4</td>
    <td>5 6 7</td>
    <td>8</td>
    <td>1 2 3 4 5 6 7 8</td>
    <td>1 2 3 4 5 6 7 8</td>
  </tr>
  <tr>
    <td>Version</td>
    <td>Type</td>
    <td>isAck</td>
    <td>Token length</td>
    <td>Message id</td>
  </tr>
  <tr><td colspan="5"></tr>
  <tr>
    <th colspan="5"><center>4 byte -> token length</center></th>
  </tr>
  <tr>
    <td colspan="5">Token (optional)</td>
  </tr>
</table>

### Topic  
<table id="topic">
  <tr>
    <th><center>1 byte</center></th>
  </tr>
  <tr>
    <td><center>Topic length</td></center>
  </tr>
  <tr>
    <td></td>
  </tr>
  <tr>
    <th>2 byte -> topic length</th>
  </tr>
  <tr>
    <td><center>Topic</center></td>
  </tr>
</table>

### Client
<table id="client">
  <tr>
    <th>1 byte</th>
    <th>2 byte</th>
  </tr>
  <tr>
    <td>Username length</td>
    <td>Password length</td>
  </tr>
  <tr>
    <td colspan="2"></td>
  </tr>
  <tr>
    <th colspan="2">3 byte -> username length</th>
  </tr>
  <tr>
    <td colspan="2">Username</td>
  </tr>
  <tr>
    <th colspan="2">username length end byte -> password length</th>
  </tr>
  <tr>
    <td colspan="2">Password (optional)</td>
  </tr>
</table>

### Payload
<table id="payload">
  <tr>
    <th>Rest of bytes</td>
  </tr>
</table>

## Messages

### CONNECT
<table id="connect">
  <tr>
    <td>HEADER</td>
  </tr>
  <tr>
    <td>CLIENT (optional)</td>
  </tr>
</table>

### DISCONNECT
<table id="disconnect">
  <tr>
    <td>HEADER</td>
  </tr>
  <tr>
    <td>TOPIC (optional)</td>
  </tr>
</table>

### PUBLISH
<table id="publish">
  <tr>
    <td>HEADER</td>
  </tr>
  <tr>
    <td>TOPIC</td>
  </tr>
  <tr>
    <td>PAYLOAD</td>
  </tr>  
</table>

### SUBSCRIBE
<table id="subscribe">
  <tr>
    <td>HEADER</td>
  </tr>
  <tr>
    <td>TOPIC</td>
  </tr>
</table>

### PING
<table id="ping">
  <tr>
    <td>HEADER</td>
  </tr>
</table>  
