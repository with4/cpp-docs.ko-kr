---
title: "동적 접근자 사용 | Microsoft Docs"
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
helpviewer_keywords: 
  - "접근자[C++], 동적"
  - "동적 접근자"
ms.assetid: e5d5bfa6-2b1d-49d0-8ced-914666422431
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 동적 접근자 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

동적 접근자를 사용하면 데이터베이스 스키마\(내부 구조\)에 대해 모르더라도 데이터 소스에 액세스할 수 있습니다.  OLE DB 템플릿 라이브러리에서는 이 작업을 위해 여러 클래스를 제공합니다.  
  
 [DynamicConsumer](http://msdn.microsoft.com/ko-kr/2ccc4c61-6749-4e83-aa81-00f8009c0dc3) 샘플에서는 열 정보를 얻고 동적으로 접근자를 만들기 위해 동적 접근자 클래스를 사용하는 방법에 대해 보여 줍니다.  
  
## CDynamicAccessor 사용  
 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)를 사용하면 데이터베이스 스키마\(내부 구조\)에 대해 모르더라도 데이터 소스에 액세스할 수 있습니다.  `CDynamicAccessor` 메서드는 열 이름, 개수 및 데이터 형식 같은 열 정보를 가져옵니다.  사용자는 이 열 정보를 사용하여 런타임에 동적으로 접근자를 만듭니다.  열 정보는 이 클래스에서 만들고 관리하는 버퍼에 저장됩니다.  [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md) 메서드를 사용하면 버퍼의 데이터를 가져올 수 있습니다.  
  
## 예제  
  
### 코드  
  
```  
// Using_Dynamic_Accessors.cpp  
// compile with: /c /EHsc  
#include <stdio.h>  
#include <objbase.h>  
#include <atldbcli.h>  
  
int main( int argc, char* argv[] )  
{  
    HRESULT hr = CoInitialize( NULL );  
  
    CDataSource ds;  
    CSession ss;  
  
    CTable<CDynamicAccessor> rs;  
  
    // The following is an example initialization string:  
    hr = ds.OpenFromInitializationString(L"Provider=SQLOLEDB.1;"  
      L"Integrated Security=SSPI;Persist Security Info=False;"  
      L"Initial Catalog=Loginname;Data Source=your_data_source;"  
      L"Use Procedure for Prepare=1;Auto Translate=True;"  
      L"Packet Size=4096;Workstation ID=LOGINNAME01;"  
      L"Use Encryption for Data=False;"  
      L"Tag with column collation when possible=False");  
  
    hr = ss.Open( ds );  
    hr = rs.Open( ss, "Shippers" );  
  
    hr = rs.MoveFirst( );  
    while( SUCCEEDED( hr ) && hr != DB_S_ENDOFROWSET )  
    {  
        for( size_t i = 1; i <= rs.GetColumnCount( ); i++ )  
        {  
            DBTYPE type;  
            rs.GetColumnType( i, &type );  
            printf_s( "Column %d [%S] is of type %d\n",  
                      i, rs.GetColumnName( i ), type );   
  
            switch( type )  
            {  
                case DBTYPE_WSTR:  
                    printf_s( "value is %S\n",  
                              (WCHAR*)rs.GetValue( i ) );  
                break;  
                case DBTYPE_STR:  
                    printf_s( "value is %s\n",  
                              (CHAR*)rs.GetValue( i ) );  
                default:  
                    printf_s( "value is %d\n",  
                              *(long*)rs.GetValue( i ) );  
            }  
        }  
        hr = rs.MoveNext( );  
    }  
  
    rs.Close();     
    ss.Close();  
    ds.Close();  
    CoUninitialize();  
  
    return 0;  
}  
```  
  
## CDynamicStringAccessor 사용  
 [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)는 한 가지 중요한 방식을 제외하고는 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)처럼 동작합니다.  `CDynamicAccessor`에서는 공급자가 보고한 원시 형식으로 데이터를 요청하는 반면, `CDynamicStringAccessor`에서는 공급자가 데이터 저장소에서 액세스되는 모든 데이터를 문자열 데이터로 페치하도록 요청합니다.  특히 이것은 데이터 저장소의 내용 표시 또는 인쇄와 같이 데이터 저장소의 값을 계산할 필요가 없는 단순 작업에 적합합니다.  
  
 `CDynamicStringAccessor` 메서드를 사용하여 열 정보를 구하십시오.  사용자는 이 열 정보를 사용하여 런타임에 동적으로 접근자를 만듭니다.  열 정보는 이 클래스에서 만들고 관리하는 버퍼에 저장됩니다.  [CDynamicStringAccessor::GetString](../../data/oledb/cdynamicstringaccessor-getstring.md)을 사용하여 버퍼에서 데이터를 가져오거나 [CDynamicStringAccessor::SetString](../../data/oledb/cdynamicstringaccessor-setstring.md)을 사용하여 버퍼에 데이터를 저장합니다.  
  
## 예제  
  
### 코드  
  
```  
// Using_Dynamic_Accessors_b.cpp  
// compile with: /c /EHsc  
#include <stdio.h>  
#include <objbase.h>  
#include <atldbcli.h>  
  
int main( int argc, char* argv[] )  
{  
    HRESULT hr = CoInitialize( NULL );  
    if (hr != S_OK)  
    {  
        exit (-1);  
    }  
  
    CDataSource ds;  
    CSession ss;  
  
    CTable<CDynamicStringAccessor> rs;  
  
    // The following is an example initialization string:  
    hr = ds.OpenFromInitializationString(L"Provider=SQLOLEDB.1;"  
      L"Integrated Security=SSPI;Persist Security Info=False;"  
      L"Initial Catalog=Loginname;Data Source=your_data_source;"  
      L"Use Procedure for Prepare=1;Auto Translate=True;"  
      L"Packet Size=4096;Workstation ID=LOGINNAME01;"  
      L"Use Encryption for Data=False;"  
      L"Tag with column collation when possible=False");  
  
    hr = ss.Open( ds );  
    hr = rs.Open( ss, "Shippers" );  
  
    hr = rs.MoveFirst( );  
    while( SUCCEEDED( hr ) && hr != DB_S_ENDOFROWSET )  
    {  
        for( size_t i = 1; i <= rs.GetColumnCount( ); i++ )  
        {  
            printf_s( "column %d value is %s\n",   
                      i, rs.GetString( i ) );  
        }  
        hr = rs.MoveNext( );  
    }  
  
    rs.Close();     
    ss.Close();  
    ds.Close();  
    CoUninitialize();  
  
   return 0;  
  
}  
```  
  
## CDynamicParameterAccessor 사용  
 [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)는 `CDynamicParameterAccessor`가 [ICommandWithParameters](https://msdn.microsoft.com/en-us/library/ms712937.aspx) 인터페이스를 호출하여 설정될 매개 변수 정보를 구한다는 점을 제외하고는 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)와 유사합니다.  공급자는 소비자가 이 클래스를 사용하도록 `ICommandWithParameters`를 지원해야 합니다.  
  
 매개 변수 정보는 이 클래스에서 만들고 관리하는 버퍼에 저장됩니다.  [CDynamicParameterAccessor::GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) 및 [CDynamicParameterAccessor::GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md)을 사용하여 버퍼에서 매개 변수 데이터를 구하십시오.  
  
 이 클래스를 사용하여 SQL Server 저장 프로시저를 실행하고 출력 매개 변수 값을 구하는 방법을 설명하는 예제는 기술 자료 문서의 Q058860, "HOWTO: Execute Stored Procedure using CDynamicParameterAccessor"를 참조하십시오. Knowledge Base articles are available in the MSDN Library Visual Studio documentation or at [http:\/\/support.microsoft.com](http://support.microsoft.com/).  
  
## 참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)   
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessor 클래스](../../data/oledb/cdynamicstringaccessor-class.md)   
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [DynamicConsumer Sample](http://msdn.microsoft.com/ko-kr/2ccc4c61-6749-4e83-aa81-00f8009c0dc3)