// Jenkinsfile: scripted Jenkins pipefile
// This file was automatically generated using 'python -m vsc.install.ci'
// DO NOT EDIT MANUALLY

node {
    stage('checkout git') {
        checkout scm
        // remove untracked files (*.pyc for example)
        sh 'git clean -fxd'
    }
    stage('test') {
        sh 'python2.7 -V'
        sh 'python -m easy_install -U --user tox'
        sh 'export PATH=$PWD/.vsc-tox/bin:$PATH && export PYTHONPATH=$PWD/.vsc-tox/lib/python$(python -c "import sys; print(\\"%s.%s\\" % sys.version_info[:2])")/site-packages:$PYTHONPATH && tox -v -c tox.ini'
        sh 'rm -r $PWD/.vsc-tox'
    }
}
