<template>
  <div>
    <gov-heading size="l">Who is it for?</gov-heading>
    <gov-grid-row>
      <gov-grid-column width="one-half">
        <gov-body>
          Use this section to add details as to who this service is for. If any of these
          criteria do not apply to your service, please leave them blank.
        </gov-body>
        <gov-section-break size="l" />

        <!-- Age group -->
        <criteria-input
          :value="age_group"
          @input="$emit('update:age_group', $event); $emit('clear', 'criteria.age_group')"
          :error="errors.get('criteria.age_group')"
          id="criteria.age_group"
          label="Age of service user (if applicable)"
          hint='e.g. "This service is for people 16+", or "This service is aimed at people nearig retirement"'
        />
        <!-- /Age group -->

        <!-- Disability -->
        <criteria-input
          :value="disability"
          @input="$emit('update:disability', $event); $emit('clear', 'criteria.disability')"
          :error="errors.get('criteria.disability')"
          id="criteria.disability"
          label="Disability Requirements / Restrictions (if applicable)"
          hint='e.g. "This service is for those with MS and their carers", or "For all people with disabilities and their carers"'
        />
        <!-- /Disability -->

        <!-- Gender -->
        <criteria-input
          :value="gender"
          @input="$emit('update:gender', $event); $emit('clear', 'criteria.gender')"
          :error="errors.get('criteria.gender')"
          id="criteria.gender"
          label="Gender Specific (if applicable)"
          hint='e.g. "Women only"'
        />
        <!-- /Gender -->

        <!-- Housing -->
        <criteria-input
          :value="housing"
          @input="$emit('update:housing', $event); $emit('clear', 'criteria.housing')"
          :error="errors.get('criteria.housing')"
          id="criteria.housing"
          label="Specific Housing status/needs (if applicable)"
          hint='e.g. "For people who are homeless or at risk of homelessness"'
        />
        <!-- /Housing -->

        <!-- Income -->
        <criteria-input
          :value="income"
          @input="$emit('update:income', $event); $emit('clear', 'criteria.income')"
          :error="errors.get('criteria.income')"
          id="criteria.income"
          label="Income level (if applicable)"
          hint='e.g. "Service is aimed at people claiming benefits or with Income support"'
        />
        <!-- /Income -->

        <!-- Language -->
        <criteria-input
          :value="language"
          @input="$emit('update:language', $event); $emit('clear', 'criteria.language')"
          :error="errors.get('criteria.language')"
          id="criteria.language"
          label="Language accessability (if applicable)"
          hint='e.g. "Instructors speak English, but open to all", or "This service is available in a number of languages - please contact me for more information"'
        />
        <!-- /Language -->

        <!-- Other -->
        <criteria-input
          :value="other"
          @input="$emit('update:other', $event); $emit('clear', 'criteria.other')"
          :error="errors.get('criteria.other')"
          id="criteria.other"
          label="Any other notes as to who the service is aimed at/not appropraite for?"
          hint='e.g. "This service is open to all", or "This service is aimed at people living in Chessington"'
        />
        <!-- /Other -->

        <slot />

      </gov-grid-column>
    </gov-grid-row>
  </div>
</template>

<script>
import CriteriaInput from "@/views/services/inputs/CriteriaInput";

export default {
  name: "WhoForTab",
  components: { CriteriaInput },
  props: {
    errors: {
      required: true
    },
    age_group: {
      required: true
    },
    disability: {
      required: true
    },
    employment: {
      required: true
    },
    gender: {
      required: true
    },
    housing: {
      required: true
    },
    income: {
      required: true
    },
    language: {
      required: true
    },
    other: {
      required: true
    }
  }
};
</script>