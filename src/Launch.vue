<template>
  <div id="launch">
  </div>
</template>

<script>
import FHIR from 'fhirclient';

const urlParams = new URLSearchParams(window.location.search);
let patientId = urlParams.get('patient');
if (patientId == null) patientId = '123';
FHIR.oauth2.authorize({
    clientId: "9be2ad88-49dd-4e05-bf77-ae72ce3e513f",
    scope: "patient/Patient.read patient/Condition.read patient/Observation.read patient/Procedure.read patient/QuestionnaireResponse.read online_access openid fhirUser patient/QuestionnaireResponse.write",
    iss: "http://localhost:3000/4_0_0",
    launch: patientId
});

export default {
  name: 'Launch'
}
</script>

<style>
</style>
