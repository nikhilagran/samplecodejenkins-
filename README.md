name: Trigger Jenkins Job

on:
  push:
    branches: [main]

jobs:
  trigger-jenkins:
    runs-on: ubuntu-latest

    steps:
    - name: Trigger Jenkins Job via API
      run: |
        curl -X POST "https://your-jenkins-url.com/job/your-job-name/build?token=${{ secrets.JENKINS_TRIGGER_TOKEN }}" \
        --user "${{ secrets.JENKINS_USER }}:${{ secrets.JENKINS_API_TOKEN }}"

