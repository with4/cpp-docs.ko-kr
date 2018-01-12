---
title: "방법: ADO.NET 용 SAFEARRAY 마샬링 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- SAFEARRAY, marshaling
- ADO.NET [C++], marshaling SAFEARRAY types
ms.assetid: 1034b9d7-ecf1-40f7-a9ee-53180e87a58c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 397312a5cc8ef4869f5ce8576e5787e141c1a414
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-marshal-a-safearray-for-adonet-ccli"></a>방법: ADO.NET용 SAFEARRAY 마샬링(C++/CLI)
네이티브를 추가 하는 방법을 보여 줍니다. `SAFEARRAY` 데이터베이스 및를 네이티브 데이터베이스에서 관리 되는 배열 마샬링하는 방법을에 `SAFEARRAY`합니다.  
  
## <a name="example"></a>예  
 이 예제에서는 클래스 DatabaseClass 만들어집니다 ADO.NET 상호 작용할 수 <xref:System.Data.DataTable> 개체입니다. 이 클래스는 네이티브 c + + `class` (읽음으로써는 `ref class` 또는 `value class`). 네이티브 코드에서이 클래스를 사용 하 고 네이티브 코드에서 관리 되는 형식을 사용할 수 없습니다 되므로이 작업이 필요 합니다. 이 클래스에는 표시 된 대로 CLR를 대상으로 컴파일되는 `#pragma managed` 지시문 클래스 선언 앞에 있습니다. 이 지시문에 대 한 자세한 내용은 참조 하십시오. [관리, 관리 되지 않는](../preprocessor/managed-unmanaged.md)합니다.  
  
 DatabaseClass 클래스의 전용 멤버 참고: `gcroot<DataTable ^> table`합니다. 네이티브 형식은 관리 되는 형식을 포함 될 수 없으므로 `gcroot` 키워드는 필요 합니다. 대 한 자세한 내용은 `gcroot`, 참조 [하는 방법: 네이티브 형식에 처리 선언](../dotnet/how-to-declare-handles-in-native-types.md)합니다.  
  
 이 예제의 코드의 나머지 부분에는 표시 된 대로 네이티브 c + + 코드는는 `#pragma unmanaged` 지시문 앞에 오는 `main`합니다. 이 예제에서는에서는 DatabaseClass의 새 인스턴스를 만드는 하 고 테이블을 만들고 테이블의 일부 행을 입력 하는 메서드를 호출 합니다. 해당 네이티브 참고 `SAFEARRAY` 형식 ArrayIntsCol 데이터베이스 열에 대 한 값으로 전달 되 고 있습니다. Databaseclass 내에서 이러한 `SAFEARRAY` 에 마샬링 있는 기능을 사용 하 여 관리 되는 개체 형식은 마샬링됩니다는 <xref:System.Runtime.InteropServices?displayProperty=fullName> 네임 스페이스입니다. 메서드 특히, <xref:System.Runtime.InteropServices.Marshal.Copy%2A> 마샬링하는 데 사용 되는 `SAFEARRAY` 정수 및 메서드의 관리 되는 배열에 <xref:System.Runtime.InteropServices.Marshal.Copy%2A> 관리 되는 배열에는 정수를 마샬링하는 데 사용 되는 `SAFEARRAY`합니다.  
  
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
  
```Output  
0 1 2 3 4 5 6 7 8 9   
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
-   명령줄에서 코드를 컴파일하려면 코드 예제에서는 adonet_marshal_safearray.cpp 라는 파일에 저장 하 고 다음 문을 입력 키를 누릅니다.  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_safearray.cpp  
    ```  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 ADO.NET 관련 보안 문제에 대 한 자세한 내용은 참조 [ADO.NET 응용 프로그램 보안](/dotnet/framework/data/adonet/securing-ado-net-applications)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.InteropServices>   
 [ADO.NET를 사용 하 여 데이터 액세스 (C + + /cli CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](/dotnet/framework/data/adonet/index)   
 [상호 운용성](http://msdn.microsoft.com/en-us/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)