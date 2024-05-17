1. 一个的的动作网络，一个批评网络，一个目标动作网络，一个目标批评网络
2. replay buffer
3. for episode in M:
    1. reset
    2. for step in episode:
       1. get action from state + random N
       2. action -> next state
       3. push in replay buffer
       4. target_Q = reward + gamma * target_next_Q (state)*(1 - done) #最后一步不更新
       5. loss(critic net, target_Q)
       6. update critic net
       7. update actor net
       8. update target net
