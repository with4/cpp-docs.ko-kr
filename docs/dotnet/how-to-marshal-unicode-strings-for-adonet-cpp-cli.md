---
title: "방법: ADO.NET 용 유니코드 문자열 마샬링 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- ADO.NET [C++], marshaling Unicode strings
- Unicode [C++], strings
- strings [C++], Unicode
ms.assetid: 1da090ff-6b53-40be-841f-dc79dfe8ba10
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bf6078217218a85289602e30c1002ba861db76d2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-marshal-unicode-strings-for-adonet-ccli"></a>방법: ADO.NET용 유니코드 문자열 마샬링(C++/CLI)
네이티브 유니코드 문자열을 추가 하는 방법을 보여 줍니다 (`wchar_t *`) 데이터베이스를 마샬링하는 방법에 대 한 <xref:System.String?displayProperty=fullName> 네이티브 유니코드 문자열에 데이터베이스에서 합니다.  
  
## <a name="example"></a>예  
 이 예제에서는 클래스 DatabaseClass 만들어집니다 ADO.NET 상호 작용할 수 <xref:System.Data.DataTable> 개체입니다. 이 클래스는 네이티브 c + + `class` (읽음으로써는 `ref class` 또는 `value class`). 네이티브 코드에서이 클래스를 사용 하 고 네이티브 코드에서 관리 되는 형식을 사용할 수 없습니다 되므로이 작업이 필요 합니다. 이 클래스에는 표시 된 대로 CLR를 대상으로 컴파일되는 `#pragma managed` 지시문 클래스 선언 앞에 있습니다. 이 지시문에 대 한 자세한 내용은 참조 하십시오. [관리, 관리 되지 않는](../preprocessor/managed-unmanaged.md)합니다.  
  
 DatabaseClass 클래스의 전용 멤버 참고: `gcroot<DataTable ^> table`합니다. 네이티브 형식은 관리 되는 형식을 포함 될 수 없으므로 `gcroot` 키워드는 필요 합니다. 대 한 자세한 내용은 `gcroot`, 참조 [하는 방법: 네이티브 형식에 처리 선언](../dotnet/how-to-declare-handles-in-native-types.md)합니다.  
  
 이 예제의 코드의 나머지 부분에는 표시 된 대로 네이티브 c + + 코드는는 `#pragma unmanaged` 지시문 앞에 오는 `main`합니다. 이 예제에서는에서는 DatabaseClass의 새 인스턴스를 만드는 하 고 테이블을 만들고 테이블의 일부 행을 입력 하는 메서드를 호출 합니다. C + + 유니코드 문자열 StringCol 데이터베이스 열에 대 한 값으로 전달 되는 참고 합니다. Databaseclass 내에서 이러한 문자열에 있는 마샬링 기능을 사용 하 여 관리 되는 문자열 마샬링되는 <xref:System.Runtime.InteropServices?displayProperty=fullName> 네임 스페이스입니다. 메서드 특히, <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> 마샬링하는 데 사용는 `wchar_t *` 에 <xref:System.String>, 및 메서드 <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> 마샬링하는 데 사용 되는 <xref:System.String> 에 `wchar_t *`합니다.  
  
> [!NOTE]
>  가 할당 한 메모리 <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> 호출 하 여 해제 해야 <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> 또는 `GlobalFree`합니다.  
  
```  
// adonet_marshal_string_wide.cpp  
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
  
    void AddRow(wchar_t *stringColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        row["StringCol"] = Marshal::PtrToStringUni(  
            (IntPtr)stringColValue);  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("StringCol",  
            Type::GetType("System.String"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(wchar_t *dataColumn, wchar_t **values,  
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
            // Marshal each column value from a managed string  
            // to a wchar_t *.  
            values[i] = (wchar_t *)Marshal::StringToHGlobalUni(  
                (String ^)rows[i][columnStr]).ToPointer();  
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
    db->AddRow(L"This is string 1.");  
    db->AddRow(L"This is string 2.");  
  
    // Now retrieve the rows and display their contents.  
    wchar_t *values[MAXCOLS];  
    int len = db->GetValuesForColumn(  
        L"StringCol", values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        wcout << "StringCol: " << values[i] << endl;  
  
        // Deallocate the memory allocated using  
        // Marshal::StringToHGlobalUni.  
        GlobalFree(values[i]);  
    }  
  
    delete db;  
  
    return 0;  
}  
```  
  
```Output  
StringCol: This is string 1.  
StringCol: This is string 2.  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
-   명령줄에서 코드를 컴파일하려면 코드 예제에서는 adonet_marshal_string_wide.cpp 라는 파일에 저장 하 고 다음 문을 입력 키를 누릅니다.  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_wide.cpp  
    ```  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 ADO.NET 관련 보안 문제에 대 한 자세한 내용은 참조 [ADO.NET 응용 프로그램 보안](/dotnet/framework/data/adonet/securing-ado-net-applications)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.InteropServices>   
 [ADO.NET를 사용 하 여 데이터 액세스 (C + + /cli CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](/dotnet/framework/data/adonet/index)   
 [상호 운용성](http://msdn.microsoft.com/en-us/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)