# TIL(20.04.06)

- pytorch GPU default device 설정과 parallel processing 돌릴시 임의 GPU 설정방법

  ```python
  device=torch.device('cuda:1' if (torch.cuda.is_available() and ngpu>0) else 'cpu')
  netG=nn.DataParallel(netG,device_ids = [1, 2, 3])
  ```

  device_ids 값을 설정해주면 특정 GPU만 선택하여 돌릴수 있음

  

  

  