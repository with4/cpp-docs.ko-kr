---
title: '방법: 어셈블리에서 STL/CLR 컨테이너는 노출 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, cross-assembly issues
ms.assetid: 87efb41b-3db3-4498-a2e7-f3ef8a99f04d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 58edb96d3947cc5694731d78c6aa71a855ef7aa9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33140175"
---
# <a name="how-to-expose-an-stlclr-container-from-an-assembly"></a>방법: 어셈블리에서 STL/CLR 컨테이너 노출
와 같은 STL/CLR 컨테이너 `list` 및 `map` 템플릿 ref 클래스로 구현 됩니다. 컴파일 타임에 c + + 템플릿을 인스턴스화할 수 있습니다, 때문에 동일한 시그니처가 하지만 않는 다른 어셈블리에 두 개의 템플릿 클래스는 실제로 다른 형식입니다. 즉, 다른 어셈블리에서 템플릿 클래스를 사용할 수 없습니다.  
  
 STL/CLR 컨테이너 수 있게 하는 어셈블리 간 공유를 제네릭 인터페이스를 구현 <xref:System.Collections.Generic.ICollection%601>합니다. 이 제네릭 인터페이스를 사용 하 여 모든 언어를 지 원하는 c + +, C# 및 Visual Basic의 경우를 비롯 한 제네릭 STL/CLR 컨테이너를 액세스할 수 있습니다.  
  
 이 항목에서는 명명 된 c + + 어셈블리를 작성 하는 몇 가지 STL/CLR 컨테이너 요소에 표시 하는 방법을 보여 줍니다 `StlClrClassLibrary`합니다. 두 어셈블리에 액세스할 수 알아보겠습니다 `StlClrClassLibrary`합니다. 첫 번째 어셈블리 c + + 및 C#에서 두 번째로 작성 됩니다.  
  
 두 어셈블리는 c + +로 작성 하는 경우를 사용 하 여 컨테이너의 제네릭 인터페이스에 액세스할 수 있습니다는 `generic_container` typedef입니다. 예를 들어 형식의 컨테이너가 있는 `cliext::vector<int>`, 해당 제네릭 인터페이스는 다음: `cliext::vector<int>::generic_container`합니다. 사용 하 여 제네릭 인터페이스는 반복기를 가져올 수는 마찬가지로,는 `generic_iterator` 다음과 같이 typedef: `cliext::vector<int>::generic_iterator`합니다.  
  
 C + + 헤더 파일에 이러한 형식 정의 선언, 이후 다른 언어로 작성 된 어셈블리에 사용할 수 없습니다. 따라서에 대 한 제네릭 인터페이스에 액세스 하려면 `cliext::vector<int>` C# 또는 다른.NET 언어를 사용 하 여 `System.Collections.Generic.ICollection<int>`합니다. 사용 하 여이 컬렉션을 반복 하는 `foreach` 루프입니다.  
  
 다음 표에서 각 STL/CLR 컨테이너를 구현 하는 제네릭 인터페이스를 보여 줍니다.  
  
|STL/CLR 컨테이너|제네릭 인터페이스|  
|------------------------|-----------------------|  
|e q u e < T\>|C t i o < T\>|  
|hash_map < K, V >|IDictionary < K, V >|  
|hash_multimap < K, V >|IDictionary < K, V >|  
|hash_multiset < T\>|C t i o < T\>|  
|hash_set < T\>|C t i o < T\>|  
|목록 < T\>|C t i o < T\>|  
|지도 < K, V >|IDictionary < K, V >|  
|multimap < K, V >|IDictionary < K, V >|  
|multiset < T\>|C t i o < T\>|  
|설정 < T\>|C t i o < T\>|  
|벡터 < T\>|C t i o < T\>|  
  
> [!NOTE]
>  때문에 `queue`, `priority_queue`, 및 `stack` 컨테이너 반복기를 지원 하지 않으므로, 제네릭 인터페이스를 구현 하지 않는 하며 어셈블리 간 액세스 될 수 없습니다.  
  
## <a name="example-1"></a>예제 1  
  
### <a name="description"></a>설명  
 이 예제에서는 개인 STL/CLR 멤버 데이터를 포함 하는 c + + 클래스를 선언 합니다. 클래스의 개인 컬렉션에 대 한 액세스 권한을 부여 하는 공용 메서드를 선언 합니다. 두 가지 방법으로 c + + 클라이언트에 대 한 하나, 하나는 다른.NET 클라이언트에 대 한 수행합니다.  
  
### <a name="code"></a>코드  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## <a name="example-2"></a>예제 2  
  
### <a name="description"></a>설명  
 이 예제에서는 예 1에서 선언 된 클래스를 구현 했습니다. 이 클래스 라이브러리를 사용 하는 클라이언트에 대 한 순서, 매니페스트 도구 사용 **mt.exe** DLL에 매니페스트 파일을 포함 합니다. 자세한 내용은 코드 주석을 참조 합니다.  
  
 매니페스트 도구, 및 side-by-side-어셈블리에 대 한 자세한 내용은 참조 하십시오. [건물 C/c + + 격리 된 응용 프로그램 및 side-by-side-어셈블리](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)합니다.  
  
### <a name="code"></a>코드  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## <a name="example-3"></a>예제 3  
  
### <a name="description"></a>설명  
 이 예제에서는 예 1과 2에서 만든 클래스 라이브러리를 사용 하는 c + + 클라이언트를 만듭니다. 사용 하 여이 클라이언트는 `generic_container` 컨테이너를 반복 하 고 콘텐츠를 표시 하는 STL/CLR 컨테이너의 형식 정의 합니다.  
  
### <a name="code"></a>코드  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
### <a name="output"></a>출력  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
## <a name="example-4"></a>예제 4  
  
### <a name="description"></a>설명  
 이 예제에서는 예 1과 2에서 만든 클래스 라이브러리를 사용 하는 C# 클라이언트를 만듭니다. 사용 하 여이 클라이언트는 <xref:System.Collections.Generic.ICollection%601> STL/CLR 컨테이너는 컨테이너를 반복 하 고 콘텐츠를 표시 하는 방법입니다.  
  
### <a name="code"></a>코드  
  
```  
// CsConsoleApp.cs  
// compile with: /r:Microsoft.VisualC.STLCLR.dll /r:StlClrClassLibrary.dll /r:System.dll  
  
using System;  
using System.Collections.Generic;  
using StlClrClassLibrary;  
using cliext;  
  
namespace CsConsoleApp  
{  
    class Program  
    {  
        static int Main(string[] args)  
        {  
            StlClrClass theClass = new StlClrClass();  
  
            Console.WriteLine("cliext::deque contents:");  
            ICollection<char> iCollChar = theClass.GetDequeCs();  
            foreach (char c in iCollChar)  
            {  
                Console.WriteLine(c);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::list contents:");  
            ICollection<float> iCollFloat = theClass.GetListCs();  
            foreach (float f in iCollFloat)  
            {  
                Console.WriteLine(f);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::map contents:");  
            IDictionary<int, string> iDict = theClass.GetMapCs();  
            foreach (KeyValuePair<int, string> kvp in iDict)  
            {  
                Console.WriteLine("{0} {1}", kvp.Key, kvp.Value);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::set contents:");  
            ICollection<double> iCollDouble = theClass.GetSetCs();  
            foreach (double d in iCollDouble)  
            {  
                Console.WriteLine(d);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::vector contents:");  
            ICollection<int> iCollInt = theClass.GetVectorCs();  
            foreach (int i in iCollInt)  
            {  
                Console.WriteLine(i);  
            }  
            Console.WriteLine();  
  
            return 0;  
        }  
    }  
}  
```  
  
### <a name="output"></a>출력  
  
```  
cliext::deque contents:  
a  
b  
  
cliext::list contents:  
3.14159  
2.71828  
  
cliext::map contents:  
0 Hello  
1 World  
  
cliext::set contents:  
2.71828  
3.14159  
  
cliext::vector contents:  
10  
20  
```  
  
## <a name="see-also"></a>참고 항목  
 [STL/CLR 라이브러리 참조](../dotnet/stl-clr-library-reference.md)