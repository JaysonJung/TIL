# TIL(20.06.04)

- 쓸일은 많은데 쓸때마다 까먹는 numpy 조건에 따른 indexing

  - np.where(condition,true,false) : 조건문에 만족할경우 true값, 아닐 경우 false값
  - np.where(condition) : 조건문에 만족하는 index return
  - 다중 조건문을 걸 경우 Bit operator 로 사용 (&,|)
  - 2D 이상일경우 튜플로 리턴 dim 순서로 인덱스를 return 하는듯하다

- 랜덤 마스크 생성

  - ```python
    random_mask=np.random.randint(0,2,size=(shape of mask))
    #apply the mask
    masked_array=np.ma.array(face,mask=random_mask)
    ```

- 리스트 두개의 elements들을 combination해야 할경우

  - ```python
    a=[1,2,3]
    b=[a,b,c]
    comb_a_b=list(zip(a*len(b),b*len(a)))
    #[1,a],[1,b],[1,c]
    #[2,a],[2,b],[2,c]
    #[3,a],[3,b],[3,c]
    ```

- pandas concat

  - parameter 중에서  ignore_index는 보통True로 놓는게 정신건강에 편함
  - 나중에 새로에 index 주는게 편하다

- pandas df.columns=columns_name

  - 내가 만들어놓은 데이터 프레임 column들 이름 바꾸고 싶을때
  - 혹은 pandas의 rename 함수 써도 좋음

- pandas to_csv

  - parameter 중에서 index는 False로 놓거나 임의로 지정해줘야 나중에 'Unknown: 0'안생기고 편함

- pytorch gpu설정

  - ```python
    netGenerator=Generator(ngpu).to(device)#모델 생성하면서 GPU에 올리기
    #device에 'GPU'정보 담겨있음
    if(device.type=='cuda') and (ngpu>1):
        netGenerator=nn.DataParallel(netGenerator,device_ids = [1, 2, 3])
    #GPU 임의로 번호 지정해서 돌릴수 있도록 해줌
    netGenerator.apply(weights_init)
    #원하는 weight initializer로 지정
    ```

    