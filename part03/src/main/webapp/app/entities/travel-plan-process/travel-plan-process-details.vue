<template>
  <div class="row justify-content-center">
    <div class="col-10">
      <div v-if="travelPlanProcess.processInstance">
        <h2 class="jh-entity-heading" data-cy="travelPlanProcessDetailsHeading">
          <span v-text="$t('travelPlan03App.travelPlanProcess.detail.title')">TravelPlanProcess</span> {{ travelPlanProcess.id }}
        </h2>
        <akip-show-process-instance :processInstance="travelPlanProcess.processInstance">
          <template v-slot:title>
            <span v-text="$t('travelPlan03App.travelPlanProcess.detail.title')">TravelPlanProcess</span> #{{ travelPlanProcess.id }}
          </template>
          <template v-slot:details>
            <div class="card" v-if="travelPlanProcess.travelPlan">
              <h5 class="card-header">
                <span class="title"> Travel Plan #{{ travelPlanProcess.travelPlan.id }} </span>
              </h5>
              <div class="card-body">
                <div class="form-group">
                  <label class="form-control-label" v-text="$t('travelPlan03App.travelPlanProcess.name')">name</label>
                  <input
                    readonly
                    type="text"
                    class="form-control form-control-sm"
                    name="name"
                    id="travel-plan-name"
                    data-cy="name"
                    v-model="travelPlanProcess.travelPlan.name"
                  />
                </div>
              </div>
              <div class="card-body">
                <div class="form-group">
                  <label class="form-control-label" v-text="$t('travelPlan03App.travelPlanProcess.startDate')">startDate</label>
                  <input
                    readonly
                    type="text"
                    class="form-control form-control-sm"
                    name="startDate"
                    id="travel-plan-startDate"
                    data-cy="startDate"
                    v-model="travelPlanProcess.travelPlan.startDate"
                  />
                </div>
              </div>
              <div class="card-body">
                <div class="form-group">
                  <label class="form-control-label" v-text="$t('travelPlan03App.travelPlanProcess.endDate')">endDate</label>
                  <input
                    readonly
                    type="text"
                    class="form-control form-control-sm"
                    name="endDate"
                    id="travel-plan-endDate"
                    data-cy="endDate"
                    v-model="travelPlanProcess.travelPlan.endDate"
                  />
                </div>
              </div>
              <div class="card-body">
                <div class="form-group">
                  <label class="form-control-label" v-text="$t('travelPlan03App.travelPlanProcess.hotelName')">hotelName</label>
                  <input
                    readonly
                    type="text"
                    class="form-control form-control-sm"
                    name="hotelName"
                    id="travel-plan-hotelName"
                    data-cy="hotelName"
                    v-model="travelPlanProcess.travelPlan.hotelName"
                  />
                </div>
              </div>
              <div class="card-body">
                <div class="form-group">
                  <label class="form-control-label" v-text="$t('travelPlan03App.travelPlanProcess.hotelBookingNumber')"
                    >hotelBookingNumber</label
                  >
                  <input
                    readonly
                    type="text"
                    class="form-control form-control-sm"
                    name="hotelBookingNumber"
                    id="travel-plan-hotelBookingNumber"
                    data-cy="hotelBookingNumber"
                    v-model="travelPlanProcess.travelPlan.hotelBookingNumber"
                  />
                </div>
              </div>
              <div class="card-body">
                <div class="form-group">
                  <label class="form-control-label" v-text="$t('travelPlan03App.travelPlanProcess.airlineCompanyName')"
                    >airlineCompanyName</label
                  >
                  <input
                    readonly
                    type="text"
                    class="form-control form-control-sm"
                    name="airlineCompanyName"
                    id="travel-plan-airlineCompanyName"
                    data-cy="airlineCompanyName"
                    v-model="travelPlanProcess.travelPlan.airlineCompanyName"
                  />
                </div>
              </div>
              <div class="card-body">
                <div class="form-group">
                  <label class="form-control-label" v-text="$t('travelPlan03App.travelPlanProcess.airlineTicketNumber')"
                    >airlineTicketNumber</label
                  >
                  <input
                    readonly
                    type="text"
                    class="form-control form-control-sm"
                    name="airlineTicketNumber"
                    id="travel-plan-airlineTicketNumber"
                    data-cy="airlineTicketNumber"
                    v-model="travelPlanProcess.travelPlan.airlineTicketNumber"
                  />
                </div>
              </div>
              <div class="card-body">
                <div class="form-group">
                  <label class="form-control-label" v-text="$t('travelPlan03App.travelPlanProcess.carCompanyName')">carCompanyName</label>
                  <input
                    readonly
                    type="text"
                    class="form-control form-control-sm"
                    name="carCompanyName"
                    id="travel-plan-carCompanyName"
                    data-cy="carCompanyName"
                    v-model="travelPlanProcess.travelPlan.carCompanyName"
                  />
                </div>
              </div>
              <div class="card-body">
                <div class="form-group">
                  <label class="form-control-label" v-text="$t('travelPlan03App.travelPlanProcess.carBookingNumber')"
                    >carBookingNumber</label
                  >
                  <input
                    readonly
                    type="text"
                    class="form-control form-control-sm"
                    name="carBookingNumber"
                    id="travel-plan-carBookingNumber"
                    data-cy="carBookingNumber"
                    v-model="travelPlanProcess.travelPlan.carBookingNumber"
                  />
                </div>
              </div>
            </div>
          </template>
        </akip-show-process-instance>
        <br />
        <button type="submit" v-on:click.prevent="previousState()" class="btn btn-info" data-cy="entityDetailsBackButton">
          <font-awesome-icon icon="arrow-left"></font-awesome-icon>&nbsp;<span v-text="$t('entity.action.back')"> Back</span>
        </button>
      </div>
    </div>
  </div>
</template>

<script lang="ts" src="./travel-plan-process-details.component.ts"></script>
