# test-gcp
TEST git
La doc:

Note 1: l'api cloud function n'a pas besoin d'être activée
Mais il faut bien "Définissez le rôle Développeur Cloud Functions sur l'état Activé." pour le compte de service cloudbuild


Note 2: https://medium.com/google-cloud/triggering-cloud-functions-deployments-97691f9b5416
Il manque un truc dans la doc !

Pour que ça fonctionne, il faut faire ça: https://cloud.google.com/functions/docs/reference/iam/roles#adding_the_iam_service_account_user_role_to_the_runtime_service_account

Comme ceci:
gcloud iam service-accounts add-iam-policy-binding mestest-2222222@appspot.gserviceaccount.com --member=serviceAccount:1234567890@cloudbuild.gserviceaccount.com --role=roles/iam.serviceAccountUser                         
Updated IAM policy for serviceAccount mestest-2222222@appspot.gserviceaccount.com.
bindings:
- members:
  - serviceAccount:1234567890@cloudbuild.gserviceaccount.com
  role: roles/iam.serviceAccountUser

C'est ce qui est dit dans le message d'erreur, mais il faut bien mettre --member=serviceAccount:blablabla...
