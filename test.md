<table border="1">
<tbody>
<tr>
<th bgcolor="lightgrey">Name</th>
<th bgcolor="lightgrey">Protocol</th>
<th bgcolor="lightgrey">Description</th>
</tr>
<tr>
<td align="center">state</td>
<td align="center">IB/IBoE/iWARP</td>
<td>The logical port state. It can be one of the following enumerated values:</p>
<ul>
<li><strong>IBV_PORT_NOP</strong> - Reserved value, which shouldn't be observed</li>
<li><strong>IBV_PORT_DOWN</strong> - Logical link is down. The physical link of the port isn't up. In this state, the link layer discards all packets presented to it for transmission</li>
<li><strong>IBV_PORT_INIT</strong> - Logical link is Initializing. The physical link of the port is up, but the SM haven't yet configured the logical link. In this state, the link layer can only receive and transmit SMPs and flow control link packets, other types of packets presented to it for transmission are discarded</li>
<li><strong>IBV_PORT_ARMED</strong> - Logical link is Armed. The physical link of the port is up, but the SM haven't yet fully configured the logical link. In this state, the link layer can receive and transmit SMPs and flow control link packets, other types of packets can be received, but discards non SMP packets for sending</li>
<li><strong>IBV_PORT_ACTIVE</strong> - Logical link is Active. The link layer can transmit and receive all packet types</li>
<li><strong>IBV_PORT_ACTIVE_DEFER</strong> - Logical link is in Active Deferred. The logical link was Active, but the physical link suffered from a failure. If the error will be recovered within a timeout, the logical link will return to <strong>IBV_PORT_ACTIVE</strong>, otherwise it will move to <strong>IBV_PORT_DOWN</strong></li>
</ul>
</td>
</tr>
<tr>
<td align="center">max_mtu</td>
<td align="center">IB/IBoE/iWARP</td>
<td>Maximum MTU supported by this port. It can be one of the following enumerated values:</p>
<ul>
<li><strong>IBV_MTU_256</strong> - MTU is 256 bytes</li>
<li><strong>IBV_MTU_512</strong> - MTU is 512 bytes</li>
<li><strong>IBV_MTU_1024</strong> - MTU is 1024 bytes</li>
<li><strong>IBV_MTU_2048</strong> - MTU is 2048 bytes</li>
<li><strong>IBV_MTU_4096</strong> - MTU is 4096 bytes</li>
</ul>
</td>
</tr>
<tr>
<td align="center">active_mtu</td>
<td align="center">IB/IBoE/iWARP</td>
<td>Active maximum MTU enabled on this port to transmit and receive. It can be one of the following enumerated values which specified for <strong>max_mtu</strong>. This value specify the maximum message size that can be configured in UC/RC QPs and the maximum message size that an UD QP can transmit</td>
</tr>
<tr>
<td align="center">gid_tbl_len</td>
<td align="center">IB/IBoE/iWARP</td>
<td>Length of the Source GID Table of this port</td>
</tr>
<tr>
<td align="center">port_cap_flags</td>
<td align="center">IB/IBoE/iWARP</td>
<td>Port's supported capabilities as bitwise ORed of the following numeric values since those values aren't enumerated:</p>
<ul>
<li><strong>1 << 1</strong>   - Indication that the SM that manages the subnet sending the packets from this port</li>
<li><strong>1 << 10</strong> - Indication that there is an SM which isn't active in this port</li>
<li><strong>1 << 17</strong> - Indication that an SNMP Tunneling agent is listening on this port<strong><br />
</strong></li>
<li><strong>1 << 19</strong> - Indication that a Device Management agent is listening on this port</li>
<li><strong>1 << 20</strong> - Indication that a Vendor specific agent is listening on this port</li>
<li><strong>1 << 25</strong> - Indication that this port capable of generating the <strong>IBV_EVENT_CLIENT_REREGISTER</strong> asynchronous event</li>
</ul>
</td>
</tr>
<tr>
<td align="center">max_msg_sz</td>
<td align="center">IB/IBoE/iWARP</td>
<td>Maximum message size supported by this port</td>
</tr>
<tr>
<td align="center">bad_pkey_cntr</td>
<td align="center">IB/IBoE</td>
<td>Bad P_Key counter of the port, if supported by the device (<strong>IBV_DEVICE_BAD_PKEY_CNTR</strong> is set in dev_cap.device_cap_flags)</td>
</tr>
<tr>
<td align="center">qkey_viol_cntr</td>
<td align="center">IB/IBoE</td>
<td>Q_Key violations packets of the port, if supported by the device (<strong>IBV_DEVICE_BAD_QKEY_CNTR</strong> is set in dev_cap.device_cap_flags)</td>
</tr>
<tr>
<td align="center">pkey_tbl_len</td>
<td align="center">IB/IBoE*/iWARP*</td>
<td>Length of the partition table of this port</td>
</tr>
<tr>
<td align="center">lid</td>
<td align="center">IB</td>
<td>The base LID of this port, valid only if <strong>state</strong> is <strong>IBV_PORT_ARMED</strong> or <strong>IBV_PORT_ACTIVE</strong></td>
</tr>
<tr>
<td align="center">sm_lid</td>
<td align="center">IB</td>
<td>The LID of the SM that manages this port</td>
</tr>
<tr>
<td align="center">lmc</td>
<td align="center">IB</td>
<td>Port LID mask of this port (used in multipath), valid only if <strong>state</strong> is <strong>IBV_PORT_ARMED</strong> or <strong>IBV_PORT_ACTIVE</strong></td>
</tr>
<tr>
<td align="center">max_vl_num</td>
<td align="center">IB</td>
<td>The maximum number of VLs supported by this port. There isn't any enumeration of this value, and the numeric value can be one of the following:</p>
<ul>
<li><strong>1</strong> - 1 VL: VL0</li>
<li><strong>2</strong> - 2 VLs: VL0, VL1</li>
<li><strong>3</strong> - 4 VLs: VL0 - VL3</li>
<li><strong>4</strong> - 8 VLs: VL0 - VL7</li>
<li><strong>5</strong> - 15 VLs: VL0 - VL14</li>
</ul>
</td>
</tr>
<tr>
<td align="center">sm_sl</td>
<td align="center">IB</td>
<td>The SL of the SM that manages this port</td>
</tr>
<tr>
<td align="center">subnet_timeout</td>
<td align="center">IB</td>
<td>Specifies the maximum expected subnet propagation delay, which depends upon the configuration of the switches, to reach any other port in the subnet and also used to determine the maximum rate which SubnTrap()s can be sent from this port.<br />
The duration of time is calculated based on: <img src="//s0.wp.com/latex.php?latex=4.096%2A2%5E%7BSubnetTimeOut%7D&#038;bg=ffffff&#038;fg=000&#038;s=0" alt="4.096*2^{SubnetTimeOut}" title="4.096*2^{SubnetTimeOut}" class="latex" /></td>
</tr>
<tr>
<td align="center">init_type_reply</td>
<td align="center">IB</td>
<td>Value configured by the SM prior to changing the port to <strong>IBV_PORT_ACTIVE</strong> or <strong>IBV_PORT_ARMED</strong> state that indicates the type of initialization performed, if supported by the device (<strong>IBV_DEVICE_INIT_TYPE</strong> is set in dev_cap.device_cap_flags)</td>
</tr>
<tr>
<td align="center">active_width</td>
<td align="center">IB/IBoE*/iWARP*</td>
<td>The active link width of this port. There isn't any enumeration of this value, and the numeric value can be one of the following:</p>
<ul>
<li><strong>1</strong> - 1x</li>
<li><strong>2</strong> - 4x</li>
<li><strong>4</strong> - 8x</li>
<li><strong>8</strong> - 12x</li>
</ul>
</td>
</tr>
<tr>
<td align="center">active_speed</td>
<td align="center">IB/IBoE*/iWARP*</td>
<td>The active link speed of this port. There isn't any enumeration of this value, and the numeric value can be one of the following:</p>
<ul>
<li><strong>1</strong> - 2.5 Gbps</li>
<li><strong>2</strong> - 5.0 Gbps</li>
<li><strong>4</strong> - 10.0 Gbps</li>
<li><strong>8</strong> - 10.0 Gbps</li>
<li><strong>16</strong> - 14.0 Gbps</li>
<li><strong>32</strong> - 25.0 Gbps</li>
</ul>
</td>
</tr>
<tr>
<td align="center">phys_state</td>
<td align="center">IB</td>
<td>The physical link status. There isn't any enumeration for this value, and the numeric value can be one of the following:</p>
<ul>
<li><strong>1</strong> - Sleep: The port drives its output to quiescent levels and does not respond to received data. In this state, the link is deactivated  without powering off the port</li>
<li><strong>2</strong> - Polling: The port transmits training sequences and responds to receive training sequences.</li>
<li><strong>3</strong> - Disabled: The port drives its output to quiescent levels and does not respond to receive data</li>
<li><strong>4</strong> - PortConfigurationTraining: Both transmitter and receive active and the port is attempting to configure and transition to the LinkUp state</li>
<li><strong>5</strong> - LinkUp: The port is available to send and receive packets</li>
<li><strong>6</strong> - LinkErrorRecovery: Port attempts to re-synchronize the link and return it to normal operation</li>
<li><strong>7</strong> - Phytest: Port allows the transmitter and received circuitry to be tested by external test equipment for compliance with the transmitter and receiver specifications</li>
</ul>
</td>
</tr>
<tr>
<td align="center">link_layer</td>
<td align="center">IB/IBoE/iWARP</td>
<td>The link layer protocol used by this port. It can be one of the following enumerated values:</p>
<ul>
<li><strong>IBV_LINK_LAYER_UNSPECIFIED</strong> - Legacy value, used to indicate that the link layer protocol is InfiniBand</li>
<li><strong>IBV_LINK_LAYER_INFINIBAND</strong> - Link layer protocol is InfiniBand</li>
<li><strong>IBV_LINK_LAYER_ETHERNET</strong> - Link layer protocol is Ethernet, thus IBoE (or RoCE) can be used</li>
</ul>
</td>
</tr>
</tbody>
</table>