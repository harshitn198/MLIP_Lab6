pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''#!/bin/bash
                echo 'In C or Java, we can compile our program in this step'
                echo 'In Python, we can build our package here or skip this step'
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''#!/bin/bash
                echo 'Test Step: Running pytest with conda environment'

                # Initialize Conda using sudo
                sudo source ~/miniconda3/etc/profile.d/conda.sh

                # Activate the Conda environment using sudo
                sudo conda activate mlip

                # Run pytest using sudo
                sudo pytest --maxfail=1 --disable-warnings

                echo 'pytest completed successfully'
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our project'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}
