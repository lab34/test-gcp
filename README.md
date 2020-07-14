# test-gcp
Note: https://medium.com/google-cloud/triggering-cloud-functions-deployments-97691f9b5416

Pour que ça fonctionne, il faut faire ça: https://cloud.google.com/functions/docs/reference/iam/roles#adding_the_iam_service_account_user_role_to_the_runtime_service_account

Comme ceci:
gcloud iam service-accounts add-iam-policy-binding mestest-2222222@appspot.gserviceaccount.com --member=serviceAccount:1234567890@cloudbuild.gserviceaccount.com --role=roles/iam.serviceAccountUser                         
Updated IAM policy for serviceAccount mestest-2222222@appspot.gserviceaccount.com.
bindings:
- members:
  - serviceAccount:1234567890@cloudbuild.gserviceaccount.com
  role: roles/iam.serviceAccountUser
