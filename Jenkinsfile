#!/usr/bin/env groovy


pipeline {
	agent any
	options {
		skipStagesAfterUnstable()
	}
	environment {
		APPBOT_TOKEN = credentials('APPBOT_TOKEN')
	}
	stages {
		stage('Test') {
			steps {
				fastlane('quick_test')
			}
		}
	}
}

def fastlane(lane) {
	sh """#!/bin/bash -l
	rvm use 2.7
	bundle install
	bundle exec fastlane ${lane}
	"""
}
