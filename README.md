- 👋 Hi, I’m @Fdanielr
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Fdanielr/Fdanielr is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<p>DANIEL <strong> FLOREZ</strong></p>
<body>
  <h1>DAN PAGE </h1>
  <h3>Best Landing Page</h3>
  <ul>
    <a href:"https://www.instagram.com/fdanielr7/" >Images</a>
    <li><a href:"https://www.instagram.com/we.love.change/ >Bussines</a> </li>
    <li>Messages</li>
    <li>Updates</li>
    <ul/>
<html>

    <!-- Created with Pyto -->

    <head>
        <title>My page</title>
    </head>
    <body>
        <p id="content"></p>
        
        <script type="text/python">
            from htmpy import window
            
            Mi_Lista =['Bogota','Lima','Asuncion','Caracas']
            
            p = window.document.getElementById("content")
            p.innerText = "Hello World!"
        </script>
    </body>
</html>


      
</body>
Mi_Lista['Bogota','Mexico','Lima','Asuncion']




      
      

name: Python package

on: [push]

jobs:
  build:

    runs-on: ubuntu-latest
    strategy:
      matrix:
        python-version: ["3.7", "3.8", "3.9", "3.10"]

    steps:
      - uses: actions/checkout@v3
      - name: Set up Python ${{ matrix.python-version }}
        uses: actions/setup-python@v4
        with:
          python-version: ${{ matrix.python-version }}
      - name: Install dependencies
        run: |
          python -m pip install --upgrade pip
          pip install flake8 pytest
          if [ -f requirements.txt ]; then pip install -r requirements.txt; fi
      - name: Lint with flake8
        run: |
          # stop the build if there are Python syntax errors or undefined names
          flake8 . --count --select=E9,F63,F7,F82 --show-source --statistics
          # exit-zero treats all errors as warnings. The GitHub editor is 127 chars wide
          flake8 . --count --exit-zero --max-complexity=10 --max-line-length=127 --statistics
      - name: Test with pytest
        run: |
          pytest
