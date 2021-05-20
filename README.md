# 2021LoadMonitoring #
   ## **Научная работа по теме "Разработка и исследование метода управления нагрузкой на контроллер в программно-конфигурируемых сетях"** 

### В данном репозитории приводится реализация Практической части Курсовой работы ###



Краткое описание шагов для запуска:
  
  1. Пройти полный запуск RUNOS 2.0. доступный по ссылке: https://github.com/ARCCN/runos.   
           1) выполнить шаги в разделе "Build RUNOS from Source"  
           2) выполнить шаги в разделе "Install Application from Source" для установки git clone https://github.com/ARCCN/l2-learning-switch.git  
	        3) выполнить шаги в разделе "RUNOS Web UI Configuring"  
	        4) выполнить шаги в разделе "Quick RUNOS Test Using Mininet"  
	        5) запустить контроллер RUNOS 2.0:   
		            <pre> nix-shell  
		            cd build  
		            cmake ..  
		            make  
		            cd ..  
		            ./build/runos </pre>  
	        6) запуск mininet со следующей командой:  
		            <pre> sudo mn --topo=tree,depth=2,fanout=5 --switch=ovsk,protocols=OpenFlow13 --controller=remote </pre>   
		
  
  2. Загрузить runos_poller.py файл на запущенную машину с RUNOS 2.0.   
      Перед запуском программы убедиться, что установлены все библиотеки для Python:  
		         <pre> pip3 install psutil </pre>  
  
  3. В репозитории с загруженной программой runos_poller.py выполнить следующую команду: 
       <pre> ./runos_poller.py --ip 127.0.0.1 --port 8000 --interval 1 > data_2_test.csv # где data_2_test.csv выходной файл, с собираемыми данными </pre>
       
  4. Рассмотреть / запустить готовый проект *.ipynb (находящийся в папках CorrelationCoefficient и ArtificialNeuralNetwork) на https://colab.research.google.com/
   - (перед запуском в colab необходимо убедиться, что файл data_2_test.csv загружен в файлы доступные на сервере)
