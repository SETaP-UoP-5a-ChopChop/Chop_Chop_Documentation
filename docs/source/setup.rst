Setup & Installation
====================

Prerequisites
-------------

* Python 3.10+
* pip

Installation
------------

1. Clone the repository::

      git clone https://github.com/SETaP-UoP-5a-ChopChop/Chop-Chop-SETaP-Group-5a

2. Install backend dependencies::

      cd Chop-Chop-SETaP-Group-5a/backend

      pip install -r requirements.txt

3. Install frontend dependencies::

      cd ../mobile

      npm install

External Services
-----------------

This application relies on a FatSecret proxy server hosted at
``http://13.62.210.12:3001``. Ensure you have access to this
server before running the application.

Running the Backend
-------------------

To start the development server::

   python app.py