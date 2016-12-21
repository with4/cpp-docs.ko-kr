---
title: "방법: STL/CLR 컨테이너에서 .NET 컬렉션으로 변환 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STL/CLR 컨테이너[STL/CLR]"
  - "STL/CLR, .NET 컬렉션으로 변환"
ms.assetid: 70b2dfd9-869c-4e0f-9a29-b1ee0cb0d107
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: STL/CLR 컨테이너에서 .NET 컬렉션으로 변환
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This topic shows how to convert STL\/CLR containers to their equivalent .NET collections.  As an example, we show how to convert a STL\/CLR [vector](../dotnet/vector-stl-clr.md) to a .NET <xref:System.Collections.Generic.ICollection%601> and how to convert a STL\/CLR [map](../dotnet/map-stl-clr.md) to a .NET <xref:System.Collections.Generic.IDictionary%602>, but the procedure is similar for all collections and containers.  
  
### To create a collection from a container  
  
1.  다음 방법 중 하나를 사용합니다.  
  
    -   To convert part of a container, call the [make\_collection](../dotnet/make-collection-stl-clr.md) function, and pass the begin iterator and end iterator of the STL\/CLR container to be copied into the .NET collection.  This template function takes an STL\/CLR iterator as a template argument.  The first example demonstrates this method.  
  
    -   To convert an entire container, cast the container to an appropriate .NET collection interface or interface collection.  The second example demonstrates this method.  
  
## 예제  
 In this example, we create a STL\/CLR `vector` and add 5 elements to it.  Then, we create a .NET collection by calling the `make_collection` function.  Finally, we display the contents of the newly created collection.  
  
```  
// cliext_convert_vector_to_icollection.cpp  
// compile with: /clr  
  
#include <cliext/adapter>  
#include <cliext/vector>  
  
using namespace cliext;  
using namespace System;  
using namespace System::Collections::Generic;  
  
int main(array<System::String ^> ^args)  
{  
    cliext::vector<int> primeNumbersCont;  
    primeNumbersCont.push_back(2);  
    primeNumbersCont.push_back(3);  
    primeNumbersCont.push_back(5);  
    primeNumbersCont.push_back(7);  
    primeNumbersCont.push_back(11);  
  
    System::Collections::Generic::ICollection<int> ^iColl =  
        make_collection<cliext::vector<int>::iterator>(  
            primeNumbersCont.begin() + 1,  
            primeNumbersCont.end() - 1);  
  
    Console::WriteLine("The contents of the System::Collections::Generic::ICollection are:");  
    for each (int i in iColl)  
    {  
        Console::WriteLine(i);  
    }  
}  
```  
  
  **The contents of the System::Collections::Generic::ICollection are:**  
**3**  
**5**  
**7**   
## 예제  
 In this example, we create a STL\/CLR `map` and add 5 elements to it.  Then, we create a .NET <xref:System.Collections.Generic.IDictionary%602> and assign the `map` directly to it.  Finally, we display the contents of the newly created collection.  
  
```  
// cliext_convert_map_to_idictionary.cpp  
// compile with: /clr  
  
#include <cliext/adapter>  
#include <cliext/map>  
  
using namespace cliext;  
using namespace System;  
using namespace System::Collections::Generic;  
  
int main(array<System::String ^> ^args)  
{  
    cliext::map<float, int> ^aMap = gcnew cliext::map<float, int>;  
    aMap->insert(cliext::make_pair<float, int>(42.0, 42));  
    aMap->insert(cliext::make_pair<float, int>(13.0, 13));  
    aMap->insert(cliext::make_pair<float, int>(74.0, 74));  
    aMap->insert(cliext::make_pair<float, int>(22.0, 22));  
    aMap->insert(cliext::make_pair<float, int>(0.0, 0));  
  
    System::Collections::Generic::IDictionary<float, int> ^iDict = aMap;  
  
    Console::WriteLine("The contents of the IDictionary are:");  
    for each (KeyValuePair<float, int> ^kvp in iDict)  
    {  
        Console::WriteLine("Key: {0:F} Value: {1}", kvp->Key, kvp->Value);  
    }  
}  
```  
  
  **The contents of the IDictionary are:**  
**키: 0.00 값: 0**  
**키: 13.00 값: 13**  
**키: 22.00 값: 22**  
**키: 42.00 값: 42**  
**키: 74.00 값: 74**   
## 참고 항목  
 [STL\/CLR 라이브러리](../dotnet/stl-clr-library-reference.md)   
 [방법: .NET 컬렉션에서 STL\/CLR 컨테이너로 변환](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)   
 [range\_adapter](../dotnet/range-adapter-stl-clr.md)