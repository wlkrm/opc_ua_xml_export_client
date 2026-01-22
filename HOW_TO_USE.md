# Example Usage

0. Clone this repo (`git clone git@github.com:wlkrm/opc_ua_xml_export_client.git`)
1. Install nodejs https://nodejs.org/en and python, if you don't already have it
2. Install requirements (`pip install -r requirements.txt`)

3. Download and start opc ua example server
    -   In a terminal
        ```bash
        git submodule update --init --recursive
        cd Sample-Server-node-opcua 
        npm install
        npx tsc
        node ./dst/src/server.js --port 48441
        ```
4. Run the tool (in the directory of the download tool of opc_ua_xml_export_client)
    -  Open another terminal and do not close the one running the server from Step 3. You can now download the machine tool example csv:
        ```bash
        python ./NodeXmlExporter.py --values true --namespace 31 opc.tcp://localhost:48441 machinetool.csv
        ```
    -  Or the woodworking example csv:
        ```bash
        python ./NodeXmlExporter.py --values true --namespace 42 opc.tcp://localhost:48441 woodworking.csv
        ```
