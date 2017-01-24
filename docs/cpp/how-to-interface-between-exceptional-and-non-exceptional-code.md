---
title: "방법: 예외 코드와 예외가 아닌 코드 간 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: fd5bb4af-5665-46a1-a321-614b48d4061e
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 예외 코드와 예외가 아닌 코드 간 인터페이스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서는 c \+ \+ 모듈에서 일관된 예외 처리를 구현 하는 방법 및 이러한 예외 예외 경계에서 오류 코드를 변환 하는 방법을 설명합니다.  
  
 때로 c \+ \+ 모듈은 예외 \(비 예외 코드\)를 사용하지 않는 코드와 인터페이스합니다.  이러한 인터페이스는 *예외 경계*로 알려져 있습니다.  예를 들어, `CreateFile` Wind32 함수를 c \+ \+ 프로그램에서 호출하려 할 것입니다.  `CreateFile` 는 예외를 throw하지 않습니다; 대신에 `GetLastError` 함수에 의해 검색되는 오류 코드를 설정합니다.  C \+ \+ 프로그램은 사소한 경우가 아니라면, 일관 된 예외 기반의 오류 처리 정책을 지키는 것이 좋습니다..  예외가 아닌 코드와 인터페이스하기 때문에, 중단 예외를 원하지 않을 것입니다. 그리고 C \+ \+ 모듈에서 예외 및 예외가 아닌 기반 정책 혼합을 원하지 않을 것입니다.  
  
## C \+ \+에서 예외 없는 함수 호출  
 C \+ \+에서는 뛰어나지 않은 함수를 호출할 때, 오류를 감지하고 가능한 경우 예외를 throw 하는 C\+\+ 함수의 함수를 래핑할 것입니다.  래퍼 함수를 디자인할 때, 먼저 제공하기 위해 예외 보장 형식을 결정: throw를 하지 않습니다, 강력한 또는 기본.  둘째, 함수를 디자인하여 모든 리소스, 예를 들어, 예외가 throw 된 경우, 파일 처리기가 올바르게 해제되도록 합니다.  일반적으로, 스마트 포인터 또는 유사한 리소스 관리자는 리소스를 소유할 수 있습니다.  크기 조정 고려 사항에 대한 자세한 내용은 [방법: 예외 안전성을 위한 디자인](../cpp/how-to-design-for-exception-safety.md)을 참조하십시오.  
  
### 예제  
 다음 예제는 내부적으로 두 파일을 읽고 여는 Win32 `CreateFile` 및 `ReadFile` 함수 를 사용하는 C\+\+ 함수를 보여줍니다.  `File` 클래스는 파일 핸들에 대한 초기화 \(RAII\) 래퍼인 리소스 획득입니다.  생성자는 "파일을 찾을 수 없음" 상태를 감지하고 C\+\+ 모듈\(이 예제에서, `main()` 함수\) 의 호출 스택 위로 오류를 전파하기 위해 예외를 throw합니다.  `File` 개체가 완전히 생성된후 다음 예외가 발생하는 경우,, 소멸자가 자동으로 파일 핸들을 해제하도록 `CloseHandle` 을 호출합니다. \(액티브 템플릿 라이브러리 \(ATL\) `CHandle` 클래스를 같은 용도로 또는 `unique_ptr` 함께 사용자 지정 deleter를 하여 사용할 수 있습니다.\) Win32 및 CRT Api를 호출하는 함수가 오류를 검색한 다음 로컬로 정의된 `runtime_error` 클래스 로부터 파생된 `Win32Exception` 클래스를 사용하여 반환하는 `ThrowLastErrorIf` 함수를 사용하는 C\+\+ 예외를 throw합니다.  이 예제의 모든 기능은 강력한 예외 보장 합니다; 언제든지 이러한 함수에서 예외가 throw되면 리소스가 유출 되고 프로그램 상태가 수정됩니다.  
  
```cpp  
// compile with: /EHsc  
#include <Windows.h>  
#include <stdlib.h>  
#include <vector>  
#include <iostream>  
#include <string>  
#include <limits>  
#include <stdexcept>  
  
using namespace std;  
  
string FormatErrorMessage(DWORD error, const string& msg)  
{  
    static const int BUFFERLENGTH = 1024;  
    vector<char> buf(BUFFERLENGTH);  
    FormatMessageA(FORMAT_MESSAGE_FROM_SYSTEM, 0, error, 0, buf.data(),   
        BUFFERLENGTH - 1, 0);   
    return string(buf.data()) + "   ("  + msg  + ")";  
}  
  
class Win32Exception : public runtime_error  
{      
private:  
    DWORD m_error;  
public:  
    Win32Exception(DWORD error, const string& msg)  
        : runtime_error(FormatErrorMessage(error, msg)), m_error(error) { }  
  
    DWORD GetErrorCode() const { return m_error; }  
};  
  
void ThrowLastErrorIf(bool expression, const string& msg)   
{   
    if (expression) {   
        throw Win32Exception(GetLastError(), msg);   
    }   
}   
  
class File  
{  
private:  
    HANDLE m_handle;  
  
    // Declared but not defined, to avoid double closing.  
    File& operator=(const File&);  
    File(const File&);  
public:  
    explicit File(const string& filename)   
    {  
        m_handle = CreateFileA(filename.c_str(), GENERIC_READ, FILE_SHARE_READ,   
            nullptr, OPEN_EXISTING, FILE_ATTRIBUTE_READONLY, nullptr);  
        ThrowLastErrorIf(m_handle == INVALID_HANDLE_VALUE,   
            "CreateFile call failed on file named " + filename);  
    }  
  
    ~File() { CloseHandle(m_handle); }  
  
    HANDLE GetHandle() { return m_handle; }  
};  
  
size_t GetFileSizeSafe(const string& filename)  
{  
    File fobj(filename);  
    LARGE_INTEGER filesize;  
  
    BOOL result = GetFileSizeEx(fobj.GetHandle(), &filesize);  
    ThrowLastErrorIf(result == FALSE, "GetFileSizeEx failed: " + filename);  
  
    if (filesize.QuadPart < (numeric_limits<size_t>::max)()) {  
        return filesize.QuadPart;  
    } else {  
        throw;   
    }  
}  
  
vector<char> ReadFileVector(const string& filename)  
{  
    File fobj(filename);  
    size_t filesize = GetFileSizeSafe(filename);  
    DWORD bytesRead = 0;  
  
    vector<char> readbuffer(filesize);  
  
    BOOL result = ReadFile(fobj.GetHandle(), readbuffer.data(), readbuffer.size(),   
        &bytesRead, nullptr);  
    ThrowLastErrorIf(result == FALSE, "ReadFile failed: " + filename);  
  
    cout << filename << " file size: " << filesize << ", bytesRead: "   
        << bytesRead << endl;  
  
    return readbuffer;  
}  
  
bool IsFileDiff(const string& filename1, const string& filename2)   
{  
    return ReadFileVector(filename1) != ReadFileVector(filename2);  
}   
  
#include <iomanip>  
  
int main ( int argc, char* argv[] )  
{  
    string filename1("file1.txt");  
    string filename2("file2.txt");  
  
    try  
    {  
        if(argc > 2) {  
            filename1 = argv[1];  
            filename2 = argv[2];  
        }   
  
        cout << "Using file names " << filename1 << " and " << filename2 << endl;  
  
        if (IsFileDiff(filename1, filename2)) {  
            cout << "*** Files are different." << endl;  
        } else {  
            cout<< "*** Files match." << endl;  
        }  
    }  
    catch(const Win32Exception& e)  
    {          
        ios state(nullptr);  
        state.copyfmt(cout);  
        cout << e.what() << endl;  
        cout << "Error code: 0x" << hex << uppercase << setw(8) << setfill('0')   
            << e.GetErrorCode() << endl;  
        cout.copyfmt(state); // restore previous formatting  
    }  
}  
  
```  
  
## 비 코드에서 예외 코드를 호출  
 "extern C"가 C 프로그램에서 호출될 때 C\+\+ 함수가 선언됩니다.  여러 다른 언어로 작성된 코드에서 C\+\+ COM 서버를 사용할 수 있습니다.  예외 없는 코드에서 호출 되는 C\+\+의 주의 공용 함수를 구현 하는 경우, C\+\+ 함수는 예외를 호출자로 다시 전파하기 위해 허용해야 합니다.  따라서, C\+\+ 함수 처리는 다룰 수 있는 모든 예외를 특별히 감지해야 하고, 필요한 경우, 예외를 호출자가 이해하는 오류 코드로 변환해야 합니다.  모든 가능한 예외를 알고 있지 않은 경우,C\+\+ 함수는 마지막 처리기로써 `catch(…)` 블록을 갖고 있어야 합니다.  이런 경우에는, 프로그램의 상태를 알 수 없기 때문에, 호출자에게 오류를 보고 하는 것이 가장 좋습니다.  
  
 다음 예제는 `std::exception` 로 부터 파생된 예외 형식 또는 Win32예외가 throw 될수 있는 어떤 예외를 가정하는 함수를 보여줍니다.  함수는 이러한 유형의 예외를 검출하고 호출자에게 Win32 오류 코드와 오류 정보를 전파합니다.  
  
```cpp  
BOOL DiffFiles2(const string& file1, const string& file2)   
{   
    try   
    {   
        File f1(file1);   
        File f2(file2);   
        if (IsTextFileDiff(f1, f2))   
        {   
            SetLastError(MY_APPLICATION_ERROR_FILE_MISMATCH);   
            return FALSE;   
        }   
        return TRUE;   
    }   
    catch(Win32Exception& e)   
    {   
        SetLastError(e.GetErrorCode());   
    }  
  
    catch(std::exception& e)   
    {   
        SetLastError(MY_APPLICATION_GENERAL_ERROR);   
    }   
    return FALSE;   
}  
  
```  
  
 예외에서 오류 코드를 변환하는 경우, 하나의 잠재적인 문제는 예외가 저장 할 수 있는 다양한 정보를 포함하지 않는 오류 코드입니다.  제공하기 위해, throw 될 수 있는 각각 특정 형식에 대해 `catch` 블록을 제공할 수 있고 오류 코드로 변환되기 전에 예외의 자세한 기록에 로깅할 수 있습니다.  이러한 접근은 만약 같은 `catch` 블록의 집합을 여러 함수가 사용한다면 많은 코드 반복을 만들 수 있습니다.  코드의 반복을 피하기위한 좋은 방법은 이러한 블록의 리팩터링에 의해 `try` 및 `catch` 블록을 수행하는 전용 유틸리티 함수를 구현과 `try` 블록에서 차단되는 함수 개체를 허용하는 것입니다.  각 공용 함수에서, 람다 식으로 유틸리티 함수 코드를 전달합니다.  
  
```cpp  
template<typename Func>   
bool Win32ExceptionBoundary(Func&& f)   
{   
    try   
    {   
        return f();   
    }   
    catch(Win32Exception& e)   
    {   
        SetLastError(e.GetErrorCode());   
    }   
    catch(const std::exception& e)   
    {   
        SetLastError(MY_APPLICATION_GENERAL_ERROR);   
    }   
    return false;   
}  
  
```  
  
 다음 예제에서는 함수를 정의 하는 람다 식을 작성하는 방법을 보여 줍니다.  함수가 람다 식을 사용하여 "인라인"으로 정의될 때, 함수 개체로 명명되어 작성된 경우 보다 읽기가 쉽습니다.  
  
```cpp  
bool DiffFiles3(const string& file1, const string& file2)   
{   
    return Win32ExceptionBoundary([&]() -> bool  
    {   
        File f1(file1);   
        File f2(file2);   
        if (IsTextFileDiff(f1, f2))   
        {   
            SetLastError(MY_APPLICATION_ERROR_FILE_MISMATCH);   
            return false;   
        }   
        return true;   
    });   
}  
  
```  
  
 람다 식에 대한 자세한 내용은 [람다 식](../cpp/lambda-expressions-in-cpp.md)을 참조하십시오.  
  
## 참고 항목  
 [오류 및 예외 처리](../cpp/errors-and-exception-handling-modern-cpp.md)   
 [방법: 예외 안전성을 위한 디자인](../cpp/how-to-design-for-exception-safety.md)