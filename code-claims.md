##Code claims

  - Are high-level integration tests, being run against actual code
  - Have highly friendly names and descriptions
  - Provide value to users by specifying client behavior and/or performance under certain conditions
  - Are published to some special place
  - Can be run by anyone
  - Are being updated along with changes and announced

###Example

>	Synchronization of 1000 blocks is made in 10 packets for any client to receive

####Code:
	
```
#[test] 
fn chain_takes_few_steps() { 	
  let mut net = TestNet::new(3); 
  net.peer_mut(1).chain.add_blocks(1000, false); 	
  net.peer_mut(2).chain.add_blocks(1000, false); 	
  let total_steps = net.sync(); 	
  assert_eq!(total_steps, 10);
}
```
