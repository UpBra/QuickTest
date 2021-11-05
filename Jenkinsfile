#!/usr/bin/env groovy

def fastlane(lane) {
	sh """#!/bin/bash -l
	rvm use 2.7
	bundle install
	bundle exec fastlane ${lane}
	"""
}

pipeline {
	agent any
	stages {
		stage('Test') {
			steps {
				sh "printenv"
				fastlane 'quick_test'
			}
		}
	}
}
