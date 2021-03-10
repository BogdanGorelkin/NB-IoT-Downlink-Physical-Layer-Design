# NB-IoT-Downlink-Physical-Layer-Design
*Channel Modeling N-bcch Narrow Band IoT Downlink Physical Layer Design*

For the technical information of this modeling, please see page 136 of document [45820-d10.doc](https://github.com/BogdanGorelkin/NB-IoT-Downlink-Physical-Layer-Design/blob/main/36212-f40.docx).

Mostly, this project related with the problem of introducing redundancy into the message for the reliability and integrity of its transmission. Also here implemented some technicks decreasing over redundancy without influence to the integrity of a message  .

###### Short theory
Introducting redundancy into transmitted message should be done carefully. Correctly chosen mechanisms allow messages to be transmitted without errors, without transmitting over-redundant bits. In this project  was used a convolution code with combination of a puncturing.

I will clarify the principle of the convolutional encoder using a simple example. For example, we want to send the message «LUCK». If during the transmission of a message one character «*UCK» losted, then it is probably already impossible to determine the original message, perhaps it was «DUCK» or something else. After the message passes through the convolutional encoder, each character is mapped to several characters. If the convolutional encoder speed is ½, then the output message will be twice as long as «LLUUCCKK», which makes it possible to restore the original message. However, if neighboring characters are lost, which happens much more often, then the message will still be difficult to recover. By adding an interleaving block, the bits are mixed according to a certain algorithm. This increases the likelihood of recovering the original «LCK**CU» message.

To see the result of the program execution click [here](https://b.gorelkin.me/projects/n-bcch/n-bcch).
