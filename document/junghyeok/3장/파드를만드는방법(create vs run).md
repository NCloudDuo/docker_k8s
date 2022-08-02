# run command로 파드를 만들기
`kubectl run nginx-pod --image=nginx`
# create command로 파드만들기
`kubectl create deployment dpy-nginx --image=nginx`

## 두가지방식의 차이점?
+ run command는 nginx 파드 하나만생성
  + 해당 방법의경우, scale up이 불가능함. 
  + why? => deployment object로 배포된게 아니라서, replicaset이 없기때문에
  + 디플로이먼트에 속하지 않게되면, 어떤 컨트롤러도 파드를 관리하지않게된다.
  + deployment에 속한 Pod를 삭제시에는, 자동적으로 다시 만들기를 시도하지만(replicas의 수를 맞추기위해), 그게 아닐경우 그냥 삭제가됨
+ deployment는 deployment안에 파드 하나생성
