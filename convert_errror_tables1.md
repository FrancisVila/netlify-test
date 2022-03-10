{
    "title": "Transfer CFT messages: CFTB",
    "linkTitle": " messages: CFTB",
    "weight": "20"
}This topic lists the CFTBxx messages and provides a type, a description, and when applicable a consequence and corrective action.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: `CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started`

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

### Auto documented messages

Certain auto-documented messages, for example CFTA01I, CFTA02W, CFTA03E, CFTA04F, are not fully detailed as they are considered self-explanatory. The CFTAnnx messages refer to the acceleration feature on all platforms that support acceleration.

- CFTA01, CFTLOG\_SYS\_INFOR "CFTA01I &str"
- CFTA02, CFTLOG\_SYS\_WARNI "CFTA02W &str"
- CFTA03, CFTLOG\_SYS\_ERROR "CFTA03E &str"
- CFTA04, CFTLOG\_SYS\_FATAL "CFTA04F &str"

 


#### CFTB01E Error
V23 format:**` CFTB01E PART=&amp;part Context area allocation failure CS=&amp;scs`**
V24 format:**` CFTB01E PART=&amp;part Context area allocation failure CS=&amp;cs `**

**Explanation**
Cannot allocate the working area necessary for the transfer. |

**Consequence**
 In REQUESTER mode, the transfer is refused with a {{< TransferCFTtest/componentshortname  >}} 122 diagnostic code and a MALLOC protocol diagnostic message.<br /> In SERVER mode, the incoming call is rejected.<br/> In this case, as the partner's name is not known, the value UNKNOWN is displayed. |


 


#### CFTB02E Error
V23 format:**` CFTB02E PART=&amp;part TFIL Exchange buffer allocation failure CS=&amp;scs`**
V24 format:**` CFTB02E PART=&amp;part TFIL Exchange buffer allocation failure CS=&amp;cs `**

**Explanation**
Cannot allocate the working area required to exchange information between the PROTOCOL task and the FILE task. |

**Consequence**
 In REQUESTER mode, the transfer is refused with a Transfer CFT 122 code and a MALLOC protocol diagnostic message.<br/> In SERVER mode, the incoming call is rejected. In this case, as the partner's name is not known, the value UNKNOWN is displayed. |


 


#### CFTB03E Error
V23 format:**` CFTB03E PART=&amp;part Error sending data on network NCR=&amp;ncr NCS=&amp;ncs NET=&amp;net`**
V24 format:**` CFTB03E PART=&amp;part Error sending data on network NCR=&amp;ncr NCS=&amp;cs NET=&amp;net `**

**Explanation**
Cannot send a message on the network. |

**Consequence**
 The transfer is interrupted with a {{< TransferCFTtest/componentshortname  >}} 302 code and a protocol diagnostic message indicating the specific error code of the error occurring during the send request. This code is expressed in hexadecimal form. |


 


#### CFTB06E Error
V23 format:**` CFTB06E Flow control error NCR=&amp;ncr NCS=&amp;ncs NET=&amp;net`**
V24 format:**` CFTB06E PART=&amp;part Flow control error NCR=&amp;ncr NCS=&amp;cs NET=&amp;net `**

**Explanation**
Network flow control error. |


 


#### CFTB07E Error
V23 format:**` CFTB07E PART=&amp;part TFIL task Synchronization error CR=&amp;cr CS=&amp;cs`**
V24 format:**` CFTB07E PART=&amp;part TFIL task Synchronization error CR= &amp;cr CS=&amp;cs `**

**Explanation**
Problem encountered when sending an internal {{< TransferCFTtest/componentshortname  >}} message to the FILE task. |

**Consequence**
 The transfer is aborted by the protocol task (network disconnection). However, as the FILE task is not protected by a time-out, the request remains in the C status in the catalog |


 


#### CFTB08E Error
V23 format:**` CFTB08E PART=&amp;part Network release resp err NCR=&amp;ncr NCS=&amp;ncs NET=&amp;net`**
V24 format:**` CFTB08E PART=&amp;part Network release resp err NCR=&amp;ncr NCS=&amp;cs NET=&amp;net `**

**Explanation**
Cannot respond to a network disconnection indication. |

**Consequence**
 This incident has no effect on the previous transfer (whether completed or interrupted). |


 


#### CFTB09E Error
V23 format:**` CFTB09E PART=&amp;part Network connect req local err NCR=&amp;ncr NCS=&amp;ncs NET=&amp;net`**
V24 format:**` CFTB09E PART=&amp;part Network connect req local err NCR=&amp;ncr NCS=&amp;cs NET=&amp;net `**

**Explanation**
Cannot make an outgoing connection request on the network. |

**Consequence**
 For a general -6 code (maximum number of connections reached on the resource), the transfer is refused with a {{< TransferCFTtest/componentshortname  >}} 416 diagnostic code and a MAXCNX protocol diagnostic message. The transfer will be retried (minimum time-out equal to the WSCAN parameter of the CFTCAT command), without incrementing the retry counter. |


 


#### CFTB10E Error
V23 format:**` CFTB10E PART=&amp;part RECOV=&amp;recov L=&amp;local R=&amp;reason D=&amp;diag NET=&amp;net`**
V24 format:**` CFTB10E PART=&amp;part RECOV=&amp;recov L=&amp;local R=&amp;reason ld D=&amp;diag ld NET=&amp;net `**

**Explanation**
Physical connection refused. |

**Consequence**
 Depending on the source of the refusal and the RECOV code, the transfer is set to the K status (diagnostic code 303) or remains in the D status (diagnostic code 302) and will be retried. |

 


#### CFTB18E Error
V23 format:**` CFTB18E Incoming call reject error NCR=&amp;ncr NCS=&amp;ncs NET=&amp;net`**
V24 format:**` CFTB18E Incoming call reject error NCR=&amp;ncr NCS=&amp;cs NET=&amp;net `**

**Explanation**
Cannot refuse an incoming call. |


 


#### CFTB19E Error
V23 format:**` CFTB19E Incoming call accept error NCR=&amp;ncr NCS=&amp;ncs NET=&amp;net`**
V24 format:**` CFTB19E Incoming call accept error NCR=&amp;ncr NCS=&amp;cs NET=&amp;net `**

**Explanation**
Cannot accept an incoming call. |


 


V23 format:**` Warning | <span id="CFTB19E"></span>CFTB20E Invalid ETEBAC3 Card &amp;id NET=&amp;net`**
V24 format:**` CFTB20E Invalid ETEBAC3 Card &amp;id NET=&amp;net `**

**Explanation**
  |


 


#### CFTB21E Error
V23 format:**` CFTB21E PART=&amp;part MAIN task Synchronization error CR=&amp;cr CS=&amp;scs`**
V24 format:**` CFTB21E PART=&amp;part MAIN task Synchronization error CR= &amp;cr CS=&amp;cs `**

**Explanation**
Transfer CFT internal synchronization error. |

