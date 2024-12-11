#include <iostream>
#include <queue>
#include <string>
 
using namespace std;
 
// Function to add a job to the queue
void addJob(queue<string>& jobQueue, const string& job) {
    jobQueue.push(job);  // Add job to the queue
    cout << "Job '" << job << "' added to the queue." << endl;
}
 
// Function to delete a job from the queue
void deleteJob(queue<string>& jobQueue) {
    if (!jobQueue.empty()) {
        cout << "Job '" << jobQueue.front() << "' deleted from the queue." << endl;
        jobQueue.pop();  // Remove the job from the queue
    } else {
        cout << "No jobs in the queue to delete." << endl;
    }
}
 
int main() {
    queue<string> jobQueue;  // Create an empty job queue
    string job;
    int choice;
 
    // Menu to interact with the program
    do {
        cout << "\n1. Add Job to Queue" << endl;
        cout << "2. Delete Job from Queue" << endl;
        cout << "3. Exit" << endl;
        cout << "Enter your choice: ";
        cin >> choice;
        cin.ignore();  // To ignore the newline character after the choice input
 
        switch (choice) {
            case 1:
                cout << "Enter job name: ";
                getline(cin, job);
                addJob(jobQueue, job);  // Add job to the queue
                break;
            case 2:
                deleteJob(jobQueue);  // Delete job from the queue
                break;
            case 3:
                cout << "Exiting..." << endl;
                break;
            default:
                cout << "Invalid choice! Please try again." << endl;
        }
    } while (choice != 3);  // Keep running until the user chooses to exit
 
    return 0;
}
