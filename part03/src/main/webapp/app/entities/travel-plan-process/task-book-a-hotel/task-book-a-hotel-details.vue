<template>
  <div class="row justify-content-center">
    <div class="col-10">
      <h2 id="page-heading" data-cy="TaskInstanceHeading">
        <span v-text="$t('travelPlan03App.taskInstance.details.title')" id="task-instance-heading">Task Details</span>
      </h2>
      <div v-if="taskContext.taskInstance">
        <akip-show-task-instance :taskInstance="taskContext.taskInstance">
          <template v-slot:body>
            <hr />
            <div class="form-group">
              <label class="form-control-label" v-text="$t('travelPlan03App.taskBookAHotel.name')">name</label>
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
              <label class="form-control-label" v-text="$t('travelPlan03App.taskBookAHotel.startDate')">startDate</label>
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
              <label class="form-control-label" v-text="$t('travelPlan03App.taskBookAHotel.endDate')">endDate</label>
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
              <label class="form-control-label" v-text="$t('travelPlan03App.taskBookAHotel.hotelName')">hotelName</label>
              <input
                readonly
                type="text"
                class="form-control form-control-sm"
                name="hotelName"
                id="travel-plan-hotelName"
                data-cy="hotelName"
                v-model="taskContext.travelPlanProcess.travelPlan.hotelName"
              />
            </div>
            <div class="form-group">
              <label class="form-control-label" v-text="$t('travelPlan03App.taskBookAHotel.hotelBookingNumber')">hotelBookingNumber</label>
              <input
                readonly
                type="text"
                class="form-control form-control-sm"
                name="hotelBookingNumber"
                id="travel-plan-hotelBookingNumber"
                data-cy="hotelBookingNumber"
                v-model="taskContext.travelPlanProcess.travelPlan.hotelBookingNumber"
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
          :to="`/process-definition/TravelPlanProcess/task/TaskHotel/${taskContext.taskInstance.id}/execute`"
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

<script lang="ts" src="./task-book-a-hotel-details.component.ts"></script>
