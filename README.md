## 'github'에 파일 올리기  

### 1. repository와 연결시키기
* repository 생성 후 처음 연결할 때    
 `git clone 주소`  
   * 'origin'이라는 리모트 저장소가 자동으로 등록 => 저장소 이름이 'origin'  
   * 해당 위치에 repository에 있는 것들이 복사되어서 저장  

         $ git clone https://github.com/yougi8/git-github  
         
 * 이미 clone을 완료하고, 파일을 추가해서 올리는 경우  
  `git pull`  
    * github 상에서 repository의 수정이 생겼을 수 있으니, `git pull`을 사용해서 최신 정보를 업데이트 해준다.  
    
           $ git pull   
         
         
### 2. repository 이름 확인  
repository를 clone했다면 fetch와 push가 됐다는 것을 확인할 수 있다.  

         $ git remote -v  
         
### 3. 올릴 파일 확인  
* 올리고싶은 파일에 가서 bash를 실행한 후, `git status`를 실행  
* 아직 add되지 않은 것은 빨간색으로 표시된다.  
      
         $ git status  

### 4. 파일 add  
모두 add : `git add . `  
혹은 특정 파일만 add : `git add 파일명`  : 이때 파일명은 확장자까지 모두 작성. '파일'형태일 경우에는 확장자가 `/`  

         $ git add . 
        
         혹은  
         
         $ git add text.txt  
         
### 5. commit  
`git commit -m "여기에 작성"`  
   * github에 올라갈 때 간단한 설명?처럼 올라가는 멘트  
      
         $ git commit -m "first commit"  
        
### 6. push  
`git push 저장소이름 branch이름`  
   * 저장소이름은 origin 등, `git remote -v`로 확인한 이름을 말한다.  
      * 따로 설정 안했다면, origin  
   * branch 이름은 github에 파일이 위치할 공간이다.  
      * 보통 main이나 master (잘 확인하자)  
      * 새로운 branch를 만들어 그 이름을 사용하는 것도 가능  
   <img src="https://user-images.githubusercontent.com/51251702/103765306-5189cd00-5060-11eb-8119-e194ff4b2d94.PNG" width="500" height="370">  
    -> 사진의 경우, main이다.  
    
          $ git push origin master  
          
          혹은  
          
          $ git push origin main  
          
***

### 파일 올리기는 성공!  

### 7. 리모트 저장소 이름 변경  
`git remote rename 기존이름 새이름`  
         
         $ git remote rename origin study  
         
 origin으로 되어있던 이름이 study로 바뀜  
 -> push할 때 study로 사용해야함  
 
### 8. 리모트 저장소 추가  
`git remote add 이름 주소`  
  * 원하는 이름을 지정하고 repository주소를 입력하면 추가 완료!  
     
         $ git remote add new https://github.com/yougi8/new  
         
### 9. 리모트 저장소 삭제   
`git remote remove 이름`  
 
      $ git remote remove origin  
     
### 10. repository 이름 변경 후 
 * github 상에서 setting -> 원하는 이름으로 변경한다.  
 * git bash에서  `git remote set-url 리모트저장소이름 바뀐저장소주소` 하면 된다  
 
       $ git remote set-url origin https://github.com/yougi8/changed.git  
       
   -> 내 repository 이름이 changed로 바뀌었고, 그에 따라 연결된 주소도 changed로 변경시켜줌.
   
   
### 11. commit/push 취소  
 * bash에서 삭제하고 강제로 push한다.  

       $ git reset HEAD^  
       
   -> 가장 최근에 한 commit 기록을 삭제한다.  
   

       $ git commit -m "cancle"  
       
   -> commit시 나타낼 메시지 입력한다.  
   
   
       $ git push origin main -f  
       
   -> repository에 push한다.  


   
      
      
         
         
    
