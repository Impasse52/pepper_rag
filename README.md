# pepper-rag

Note that since this is mostly a proof of concept there are a few code smells:
1. It is assumed that client and server are ran from the same machine (i.e. the client looks for FastAPI on localhost);
2. Pepper's IP is hardcoded into `api.py`, although it is very easy to change.

Several dependencies (namely [qi](https://pypi.org/project/qi/)) rely on Linux. For this reason, this is the suggested operating system to run the project on. On Windows, WSL is supported and must be used in order to launch the server (`src/api.py`). 

Remember to boot into WSL if on Windows (e.g. `wsl -d ubuntu`), then:
```bash
git clone https://github.com/Impasse52/pepper_rag
cd pepper_rag
python3 -m venv pepper_rag
source pepper_rag/bin/activate
pip install -r requirements.txt # will take a long while
```


Make sure to adjust Pepper's IP in `src/api.py`. Then, the server can be launched with `fastapi run src/api.py`. The client (`src/client.py`) must be launched from the host OS (i.e. from Windows directly). This can be done by running `python3 src/client.py`, starting the recording which will then be sent to the server.
