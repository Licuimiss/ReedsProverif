# ReedsProverif
Description of the verification code of REEDS

We present a formal verification of REEDS using ProVerif. The verification ensures that REEDS provides the secrecy of the transmitted messages.
Proverif is an automatic verifier for cryptographic scheme defined in the Dolev-Yao model. In this model, the adversary is an active eavesdropper, who can add, delete, modify and delay messages on the network. In ProVerif, the cryptographic primitives are considered idealized that they are unbreakable without knowing the employed secret keys.

A scheme description in ProVerif is divided into three parts: the declarations, the process macros, and the main process. 
As described in lines 1-31 in REEDS-lc2.pv, the declaration part consists of the used types, the security properties, the cryptographic primitive functions, and the defined query. The query defined in line 27 are used to verify the confidentiality of messages transmitted between the senders and receivers. 
The second part of the ProVerif program describes the process macros for participants: sender (Lines 33-40), owner (Lines 42-56), broker(Lines 58-65), and receivers (Lines 67-72).
In the last part, the main process of the scheme is defined in lines 74-80. Finally, the running result of ProVerif is shown in the picture "proverif result of REEDS.JPG". In the picture, lines 1-2 show the results of the query "not  attacker ( meg[] )" returned by ProVerif. As we can see, the result are true, which means that the secrecy of the message "meg" transmitted between the sender and receiver is preserved by our scheme.

How to run the code？

1. Download the tool Proverif from https://bblanche.gitlabpages.inria.fr/proverif/ and extract the tool from the compressed file.

2. At the command line, switch the directory to the location where Proverif.exe is located, and then enter the command "Proverif+REEDS-lc2.pv" to run the code. The file of the source code is in the same directory as Proverif.exe.
