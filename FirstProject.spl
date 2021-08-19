{
  index=f5 (action=”blocked” OR action=”alerted”)
  | stats count(eval(action=”alerted”)) as AlertedCount 
  | stats count(eval(action=”blocked”)) as BlockedCount by src_ip,policy_name
  | sort – BlockedCount
  | iplocation src_ip
  | stats list(AlertedCount),list(BlockedCount) limit=5 by policy_name
  | head 10
}
