pipeline {
  agent any
  
  stages {
    stage("build"){
      steps {
        echo 'buiding the application ....'
        bat """
          python -m venv env
          cmd /c "env\\Scripts\\activate.bat"
          python -m pip install -r requirement.txt
          python manage.py collectstatic --noiput
          cmd /c "env\\Scripts\\deactivate.bat"
        """
      }
    }
    stage("test"){
      steps {
        echo 'testing the application ....'
        bat """
          cmd /c "env\\Scripts\\activate.bat"
          python manage.py test
          cmd /c "env\\Scripts\\deactivate.bat"
        """
      }
    }
    stage("deploy"){
      steps {
        echo 'deploying the application ....'
        bat """
          whoami
          copy * G:\\HOST
        """
      }
    }
  }
}
