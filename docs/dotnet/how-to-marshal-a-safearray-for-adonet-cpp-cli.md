---
title: "방법: ADO.NET용 SAFEARRAY 마샬링(C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ADO.NET[C++], SAFEARRAY 형식 마샬링"
  - "SAFEARRAY, 마샬링"
ms.assetid: 1034b9d7-ecf1-40f7-a9ee-53180e87a58c
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: ADO.NET용 SAFEARRAY 마샬링(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

네이티브 `SAFEARRAY`를 데이터베이스에 추가하는 방법과 데이터베이스에서 네이티브 `SAFEARRAY`로 관리되는 배열을 마샬링하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서는 ADO.NET <xref:System.Data.DataTable> 개체와 상호 작용하기 위해 DatabaseClass 클래스가 만들어집니다.  이 클래스는 네이티브 C\+\+ `class`\(`ref class` 또는 `value class`와 비교\)입니다.  이것은 네이티브 코드에서 이 클래스를 사용하려고 하기 때문에 필요합니다. 네이티브 코드에서는 관리되는 형식을 사용할 수 없습니다.  클래스 선언 앞에 있는 `#pragma managed` 지시문이 나타내듯이 이 클래스는 CLR을 대상으로 컴파일됩니다.  이 지시문에 대한 자세한 내용은 [관리되는, 관리되지 않는](../preprocessor/managed-unmanaged.md)를 참조하십시오.  
  
 DatabaseClass 클래스의 전용 멤버는 `gcroot<DataTable ^> table`입니다.  네이티브 형식에는 관리되는 형식이 포함될 수 없으므로 `gcroot` 키워드가 필요합니다.  `gcroot`에 대한 자세한 내용은 [방법: 네이티브 형식으로 핸들 선언](../dotnet/how-to-declare-handles-in-native-types.md)을 참조하십시오.  
  
 `main` 앞에 있는 `#pragma unmanaged` 지시문이 나타내듯이 이 예제에 있는 코드의 나머지 부분은 네이티브 C\+\+ 코드입니다.  이 예제에서는 DatabaseClass의 새 인스턴스를 만든 다음 해당 메서드를 호출하여 테이블을 만들고 테이블의 일부 행을 채웁니다.  네이티브 `SAFEARRAY` 형식은 데이터베이스 열 ArrayIntsCol에 대한 값으로 전달됩니다.  DatabaseClass 내에서 이러한 `SAFEARRAY` 형식은 <xref:System.Runtime.InteropServices?displayProperty=fullName> 네임스페이스의 마샬링 기능을 사용하여 관리되는 개체로 마샬링됩니다.  특히, `SAFEARRAY`를 정수 계열의 관리되는 배열로 마샬링하는 데는 <xref:System.Runtime.InteropServices.Marshal.Copy%2A> 메서드가 사용되고 정수 계열의 관리되는 배열을 `SAFEARRAY`로 마샬링하는 데는 <xref:System.Runtime.InteropServices.Marshal.Copy%2A> 메서드가 사용됩니다.  
  
```  
// adonet_marshal_safearray.cpp  
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll  
#include <comdef.h>  
#include <gcroot.h>  
#include <iostream>  
using namespace std;  
  
#using <System.Data.dll>  
using namespace System;  
using namespace System::Data;  
using namespace System::Runtime::InteropServices;  
  
#define MAXCOLS 100  
  
#pragma managed  
class DatabaseClass  
{  
public:  
    DatabaseClass() : table(nullptr) { }  
  
    void AddRow(SAFEARRAY *arrayIntsColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        int len = arrayIntsColValue->rgsabound[0].cElements;  
        array<int> ^arr = gcnew array<int>(len);  
  
        int *pData;  
        SafeArrayAccessData(arrayIntsColValue, (void **)&pData);  
        Marshal::Copy(IntPtr(pData), arr, 0, len);  
        SafeArrayUnaccessData(arrayIntsColValue);  
  
        row["ArrayIntsCol"] = arr;  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("ArrayIntsCol",  
            Type::GetType("System.Int32[]"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(wchar_t *dataColumn, SAFEARRAY **values,  
        int valuesLength)  
    {  
        // Marshal the name of the column to a managed  
        // String.  
        String ^columnStr = Marshal::PtrToStringUni(  
                (IntPtr)dataColumn);  
  
        // Get all rows in the table.  
        array<DataRow ^> ^rows = table->Select();  
        int len = rows->Length;  
        len = (len > valuesLength) ? valuesLength : len;  
        for (int i = 0; i < len; i++)  
        {  
            // Marshal each column value from a managed array  
            // of Int32s to a SAFEARRAY of type VT_I4.  
            values[i] = SafeArrayCreateVector(VT_I4, 0, 10);  
            int *pData;  
            SafeArrayAccessData(values[i], (void **)&pData);  
            Marshal::Copy((array<int> ^)rows[i][columnStr], 0,  
                IntPtr(pData), 10);  
            SafeArrayUnaccessData(values[i]);  
        }  
  
        return len;  
    }  
  
private:  
    // Using gcroot, you can use a managed type in  
    // a native class.  
    gcroot<DataTable ^> table;  
};  
  
#pragma unmanaged  
int main()  
{  
    // Create a table and add a few rows to it.  
    DatabaseClass *db = new DatabaseClass();  
    db->CreateAndPopulateTable();  
  
    // Create a standard array.  
    int originalArray[] = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
  
    // Create a SAFEARRAY.  
    SAFEARRAY *psa;  
    psa = SafeArrayCreateVector(VT_I4, 0, 10);  
  
    // Copy the data from the original array to the SAFEARRAY.  
    int *pData;  
    HRESULT hr = SafeArrayAccessData(psa, (void **)&pData);  
    memcpy(pData, &originalArray, 40);  
    SafeArrayUnaccessData(psa);  
    db->AddRow(psa);  
  
    // Now retrieve the rows and display their contents.  
    SAFEARRAY *values[MAXCOLS];  
    int len = db->GetValuesForColumn(  
        L"ArrayIntsCol", values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        int *pData;  
        SafeArrayAccessData(values[i], (void **)&pData);  
        for (int j = 0; j < 10; j++)  
        {  
            cout << pData[j] << " ";  
        }  
        cout << endl;  
        SafeArrayUnaccessData(values[i]);  
  
        // Deallocate the memory allocated using  
        // SafeArrayCreateVector.  
        SafeArrayDestroy(values[i]);  
    }  
  
    SafeArrayDestroy(psa);  
    delete db;  
  
    return 0;  
}  
```  
  
  **0 1 2 3 4 5 6 7 8 9**    
## 코드 컴파일  
  
-   명령줄에서 코드를 컴파일하려면 코드 예제를 adonet\_marshal\_safearray.cpp라는 파일에 저장하고 다음 문을 입력합니다.  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_safearray.cpp  
    ```  
  
## .NET Framework 보안  
 ADO.NET과 관련된 보안 문제에 대한 자세한 내용은 [ADO.NET 응용 프로그램 보안](../Topic/Securing%20ADO.NET%20Applications.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices>   
 [데이터 액세스](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](../Topic/ADO.NET.md)   
 [Interoperability](http://msdn.microsoft.com/ko-kr/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)