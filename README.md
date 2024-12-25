# UKOBA-JOSHUA-OSEZUA..
PROJECT DOCUMENTS OF PRINTER OF PRINTING DIGITAL CURRENCY 
name: Automated API tests using Postman CLI

on: push

jobs:
  automated-api-tests:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Install Postman CLI
        run: |
          curl -o- "https://dl-cli.pstmn.io/install/linux64.sh" | sh
      - name: Login to Postman CLI
        run: postman login --with-api-key ${{ secrets.POSTMAN_API_KEY }}
      - name: Run API tests
        run: |
          postman collection run "40526119-4aed2048-854e-43d2-8d3b-f731aedf8156" -e "40526119-72432cd8-a9df-4871-89ca-1032610bdeab"
