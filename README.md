## moonwalk - Node Code

discard;
break;
continue;
Collision detection
Collision solving

float2x3 m = float2x3(0,1,5,
                      8,2,2);
[_11,_12]
[_21,_22]
[_m00,_m01]
[_m10,_m11]
[ [1][1],[1][2] ]
[ [2][1],[2][2] ]
//mul rule
mul([AxB],[BxC])=[AxC]
mul([AxB], vec->[Bx1])=[vec]
mul(vec->[1xA],[AxB])=[vec]

mul(vec,M)=mul(Tra(M),vec)

mul([AxB] MA,[BxC] MB)->GetValue(Y,X)
{
return dot( MA[Y][0-B] , MA[0-B][X] )
}

mul(World,Local)
mul(后,先)
Cmd
{
rmdir /s /q "path"
start "path.exe"
}
