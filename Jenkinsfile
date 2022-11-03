def gv
pipeline
{
  agent any;
  parameters
  {
    choice(name: 'VERSION', choices: ['1.0.0','1.0.1','1.0.2'], description: 'List of versions')
    booleanParam(name: 'ExecuteTest', defaultValue: true, description: '')
  }
  stages
  {
    stage("init")
    {
      steps{
        script{
          gv = load "script.groovy"
        }
      }
    }

    stage("Build"){
      steps{
        script
        {
          gv.build()
        }
      }
    }

    stage("Test"){
      when{
        expression{
          params.ExecuteTest
        }
      }
      steps{
        script{
          gv.test()
        }
      }
    }

    stage("Deploy"){
//       when{
//         expression{
//           BRANCH_NAME == "master"
//         }
//       }
      steps{
        script{
          gv.deploy()
        }
      }
    }
  }
}
