	# reproducibility-tutorial

## Install stuff...

	# Clone repo
	cd /scratch
	git clone https://github.com/kokbent/reproducibility-tutorial.git
	
	# Install miniconda
	wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
	bash Miniconda3-latest-Linux-x86_64.sh -b -p /opt/conda
	ln -s /opt/conda/pkgs/*/bin/* /bin
	ln -s /opt/conda/pkgs/*/lib/* /usr/lib
	
	# Install Jupyter Notebook
	/opt/conda/bin/conda install -c conda-forge -y jupyterlab=1.2.3
	/opt/conda/bin/conda install -c conda-forge -y nodejs=10.13.0
	/opt/conda/bin/pip install bash_kernel
	/opt/conda/bin/pip install ipykernel
	/opt/conda/bin/python3 -m bash_kernel.install
	/opt/conda/bin/jupyter lab --no-browser --allow-root --ip=0.0.0.0 --NotebookApp.token='' --NotebookApp.password='' --notebook-dir='/scratch/reproducibility-tutorial/'
	
	# Install snakemake
	/opt/conda/bin/conda install -c bioconda -c conda-forge -y snakemake=5.8.1
	
	# Something Docker (I already installed...)
	docker image ls
	docker start hello-world
	ln -s /opt/conda/bin/* /bin
	ln -s /opt/conda/lib/* /usr/lib
	
	# verify the installation
	snakemake --version
	docker run hello-world
