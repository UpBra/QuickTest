#!/usr/bin/env groovy

def fastlane(lane) {
	sh """#!/bin/bash -l
	rvm use 2.7
	bundle install
	bundle exec fastlane ${lane}
	"""
}

pipeline {
	stages {
		stage('Test') {
			steps {
				fastlane 'quick_test'
			}
		}
	}
}
