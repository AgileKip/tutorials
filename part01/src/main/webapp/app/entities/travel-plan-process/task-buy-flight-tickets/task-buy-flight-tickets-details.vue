<template>
  <div class="row justify-content-center">
    <div class="col-10">
      <h2 id="page-heading" data-cy="TaskInstanceHeading">
        <span v-text="$t('travelPlanTutorialApp.taskInstance.details.title')" id="task-instance-heading">Task Details</span>
      </h2>
      <div v-if="taskContext.taskInstance">
        <akip-show-task-instance :taskInstance="taskContext.taskInstance">
          <template v-slot:body>
            <hr />
            <div class="form-group">
              <label class="form-control-label" v-text="$t('travelPlanTutorialApp.taskBuyFlightTickets.name')">name</label>
              <input
                readonly
                type="text"
                class="form-control form-control-sm"
                name="name"
                id="travel-plan-name"
                data-cy="name"
                v-model="taskContext.travelPlanProcess.travelPlan.name"
              />
            </div>
            <div class="form-group">
              <label class="form-control-label" v-text="$t('travelPlanTutorialApp.taskBuyFlightTickets.startDate')">startDate</label>
              <input
                readonly
                type="text"
                class="form-control form-control-sm"
                name="startDate"
                id="travel-plan-startDate"
                data-cy="startDate"
                v-model="taskContext.travelPlanProcess.travelPlan.startDate"
              />
            </div>
            <div class="form-group">
              <label class="form-control-label" v-text="$t('travelPlanTutorialApp.taskBuyFlightTickets.endDate')">endDate</label>
              <input
                readonly
                type="text"
                class="form-control form-control-sm"
                name="endDate"
                id="travel-plan-endDate"
                data-cy="endDate"
                v-model="taskContext.travelPlanProcess.travelPlan.endDate"
              />
            </div>
            <div class="form-group">
              <label class="form-control-label" v-text="$t('travelPlanTutorialApp.taskBuyFlightTickets.airlineCompanyName')"
                >airlineCompanyName</label
              >
              <input
                readonly
                type="text"
                class="form-control form-control-sm"
                name="airlineCompanyName"
                id="travel-plan-airlineCompanyName"
                data-cy="airlineCompanyName"
                v-model="taskContext.travelPlanProcess.travelPlan.airlineCompanyName"
              />
            </div>
            <div class="form-group">
              <label class="form-control-label" v-text="$t('travelPlanTutorialApp.taskBuyFlightTickets.airlineTicketNumber')"
                >airlineTicketNumber</label
              >
              <input
                readonly
                type="text"
                class="form-control form-control-sm"
                name="airlineTicketNumber"
                id="travel-plan-airlineTicketNumber"
                data-cy="airlineTicketNumber"
                v-model="taskContext.travelPlanProcess.travelPlan.airlineTicketNumber"
              />
            </div>
          </template>
        </akip-show-task-instance>
        <br />
        <button type="submit" v-on:click.prevent="previousState()" class="btn btn-info" data-cy="entityDetailsBackButton">
          <font-awesome-icon icon="arrow-left"></font-awesome-icon>&nbsp;<span v-text="$t('entity.action.back')"> Back</span>
        </button>

        <router-link
          v-if="taskContext.taskInstance.status == 'NEW' || taskContext.taskInstance.status == 'ASSIGNED'"
          :to="`/process-definition/TravelPlanProcess/task/TaskFlight/${taskContext.taskInstance.id}/execute`"
          tag="button"
          class="btn btn-primary"
          data-cy="entityDetailsButton"
        >
          <font-awesome-icon icon="play"></font-awesome-icon>&nbsp;Execute
        </router-link>
      </div>
    </div>
  </div>
</template>

<script lang="ts" src="./task-buy-flight-tickets-details.component.ts"></script>
