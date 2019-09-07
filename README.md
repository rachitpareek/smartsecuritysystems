# Smart Security Systems
<p>By Ganesh Sankaran</p>
<p>Tested on macOS Mojave and Ubuntu 18.04 LTS</p>
<hr />
<h3>Deploying the Django Web Application (macOS)</h3>
<strong>1. Obtaining the Source Code</strong>
<p>a. Clone the repository</p>
<pre>cd ~</pre>
<i><code>~</code> will be the parent directory for the repository</i>
<pre>git clone https://github.com/ganeshsankaran/smart-security-systems.git</pre>
<p>b. Obtain the pre-trained YOLOv3 model</p>
<pre>cd ~/smart-security-systems/SmartSecuritySystems/sss_v1/yolov3-coco/</pre>
<pre>wget --no-check-certificate https://pjreddie.com/media/files/yolov3.weights</pre>
<br />
<strong>2. Setting Up the PostgreSQL Server</strong>
<p>a. Install the necessary packages</p>
<i>Download and install PostgreSQL at <code>https://www.enterprisedb.com/downloads/postgres-postgresql-downloads</code></i>
<i>Then install the command line utilities for PostgreSQL</i>
<pre>brew install postgresql</pre>
<p>b. Create the database</p>
<pre>sudo su - postgres</pre>
<pre>createdb sss</pre>
<pre>exit</pre>
<br />
<strong>3. Setting up the Python Environment</strong>
<p>a. Install the necessary packages</p>
<pre>sudo pip3 install -r ~/smart-security-systems/SmartSecuritySystems/requirements.txt</pre>
<p>b. Configure <code>matplotlib</code></p>
<pre>sudo mkdir ~/.matplotlib/</pre>
<pre>sudo vim matplotlibrc</pre>
<i>Write <code>backend: TkAgg</code> to the file and save changes</i>
<br />
<br />
<strong>4. Deploying the Django Web Application</strong>
<p>a. Configure the database</p>
<pre>sudo python3 ~/smart-security-systems/SmartSecuritySystems/manage.py makemigrations</pre>
<pre>sudo python3 ~/smart-security-systems/SmartSecuritySystems/manage.py migrate</pre>
<p>b. Start the server</p>
<pre>sudo python3 ~/smart-security-systems/SmartSecuritySystems/manage.py runserver</pre>
<hr />
<h3>Deploying the Django Web Application (Ubuntu)</h3>
<strong>1. Obtaining the Source Code</strong>
<p>a. Clone the repository</p>
<pre>cd ~</pre>
<i><code>~</code> will be the parent directory for the repository</i>
<pre>git clone https://github.com/ganeshsankaran/smart-security-systems.git</pre>
<p>b. Obtain the pre-trained YOLOv3 model</p>
<pre>cd ~/smart-security-systems/SmartSecuritySystems/sss_v1/yolov3-coco/</pre>
<pre>wget --no-check-certificate https://pjreddie.com/media/files/yolov3.weights</pre>
<br />
<strong>2. Setting Up the PostgreSQL Server</strong>
<p>a. Install the necessary packages</p>
<pre>sudo apt install postgresql postgresql-contrib postgresql-server-dev-all</pre>
<p>b. Configure the <code>postgres</code> account</p>
<pre>sudo su - postgres</pre>
<pre>psql</pre>
<i>Set the password to <code>password</code></i>
<pre>\password</pre>
<pre>\q</pre>
<p>c. Create the database</p>
<pre>createdb sss</pre>
<pre>exit</pre>
<br />
<strong>3. Setting up the Python Environment</strong>
<p>a. Install the necessary packages</p>
<pre>sudo pip3 install -r ~/smart-security-systems/SmartSecuritySystems/requirements.txt</pre>
<br />
<strong>4. Deploying the Django Web Application</strong>
<p>a. Configure the database</p>
<pre>sudo python3 ~/smart-security-systems/SmartSecuritySystems/manage.py makemigrations</pre>
<pre>sudo python3 ~/smart-security-systems/SmartSecuritySystems/manage.py migrate</pre>
<p>b. Start the server</p>
<pre>sudo python3 ~/smart-security-systems/SmartSecuritySystems/manage.py runserver</pre>

