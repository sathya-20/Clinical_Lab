pipeline {
      agent any
      stages {
          stage('BuildingClinicalLabPod'){
                steps {
                    sh 'sudo kubectl create deployment clinicallab  --image=sathya15/clinical_lab:v1   --kubeconfig /root/.kube/config'
                    sh 'sudo kubectl expose deployment clinicallab --type=NodePort  --port=4444   --kubeconfig /root/.kube/config'
                    sh 'sudo kubectl get pod -o wide   --kubeconfig /root/.kube/config'
                    
                }
        }
         stage('getting pod info'){ 
               steps {
                      sh 'sudo kubectl get pod -o wide  --kubeconfig /root/.kube/config'
                      sh 'sudo kubectl get svc    --kubeconfig /root/.kube/config'
             }
        }
    }
}
