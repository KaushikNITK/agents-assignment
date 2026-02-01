## Distinguish between Passive Acknowledgment and Active Interruption
This is to interrupt the agent with the awareness of context. If agent is speaking and user gives a passive acknowledgments like okay then it should not stop or respond anything to it, rather it should just skip that word. 
But if active interruptions like wait, stop are said then agent should stop speaking.
#### Implementation
This is implemneted by having a set of passive acknowledgments in config.py and using them or adding then into .env file based on the conditions. Once agent is initiated and agent is in the middle of speech
then if user uses those passive acknowledgments then interrupt is skipped as it is detected. If it is not a passive acknowledgment then interrupted

#### Limitations and further work
This conditioning is very good and time efficient if we are having an exclusive set of passive acknowledgments or else anything outside it is considered as interrupt.

To improve this we can add a small model that can classify if given word is passive acknowledgment or active interruption and based on its output we can run the conditioning. 
This would help because now the exhaustive set we difined is no more needed meaning any phrase is recognised based on the model and then classified then this classification is used
