<div dir=rtl>بنام خدا</div>

####top

- kernels:
  - find all paths which did define:
  ```go
    jupyter --paths
  ```
  - the default path for kernel is _/usr/local/share/jupyter/kernels_ \ 
      and each kernel is _/usr/local/share/jupyter/kernels/KernelName/{kernel.json,logo.png}_
  - the structure of kernel is:
  ```json
      {
       "argv": [
        "/path/to/your/script",
        "-f",
        "{connection_file}"
       ],
       "language": "python",
       "display_name": "Python 3"
      }
  ```
  - install kernels by pip:
  ```go
    python2 -m pip install ipykernel
    python2 -m ipykernel install --user
    
    
  ```
 - [PySpark and R Kernel](http://cleverowl.uk/2016/10/15/installing-jupyter-with-the-pyspark-and-r-kernels-for-spark-development/)
 - [Scala Kernel](https://github.com/apache/incubator-toree#install)
   * after installing spark and spark
