# Sets
$`g:\ grupos\ térmicos`$ <br>
$`t:\ periodos\ horarios`$ <br>

# Parámetros
$`Precio_{t}:\ Precio\ del\ mercado\ diario`$ <br>
$`Carr_{g}:\ Coste\ de\ arranque`$ <br>
$`Caco_{g}:\ coste\ de\ acoplamiento\ (por\ la\ potencia\ de\ minimo\ técnico)`$ <br>
$`Cvar_{g}:\ coste\ variable`$ <br>
$`Cpar_{g}:\ coste\ de\ parada`$ <br>
$`EI_{g}:\ estado\ inicial\ (0/1)`$ <br>
$`PI_{g}:\ potencia\ de\ acoplamiento\ inicial`$ <br>
$`RB_{g}:\ rampa\ de\ subida`$ <br>
$`RS_{g}:\ rampa\ de\ bajada`$ <br>
$`\underline{P}{}_{g}:\ potencia\ mínima`$ <br>
$`\overline{P}{}_{g}:\ potencia\ máxima`$

# Variables
$`ct_{g,t}:\ coste térmico`$ <br>
$`p_{g,t}:\ potencia acoplada por encima del mínimo técnico`$ <br>
$`t_{g,t}:\ potencia acoplada total`$ <br>
$`v_{g,t}:\ estado de acoplamiento (0/1)`$ <br>
$`y_{g,t}:\ decisión de acoplamiento (0/1)`$ <br>
$`z_{g,t}:\ decisión de parada (0/1)`$

# Ecuaciones
$`FObj:\ Función\  objetivo\  de\  minimización\  de\  costes\  menos\  ingresos   `$ 
```math
min \ \sum_{g,t}[ct_{g,t} - t_{g,t} · Precio_{t}]
```
$`CostT_{g,t}:\ Coste\ térmico `$
```math
    ct_{g,t} = + Carr_{g} · y_{g,t}  
               + Cpar_{g} · z_{g,t} 
               + Caco_{g} · v_{g,t}                               
               + Cvar_{g} · p_{g,t}     
```
$`PotAcoT_{g,t}:\ Potencia\ acoplada\ térmica`$
```math
t_{g,t}=\underline{P}{}_{g}·v_{g,t}+p_{g,t}
```
$`AcoParPmn_{g,t}:\ parada\ a\ mínimo\ técnico`$
```math
p_{g,t} \leq  (\overline{P}{}_{g}-\underline{P}{}_{g})·(v_{g,t}-z_{g,t+1})
```
$`AcoArrPmn_{g,t}:\ arranque\ a\ mínimo\ técnico`$
```math
p_{g,t} \leq  (\overline{P}{}_{g}-\underline{P}{}_{g})·(v_{g,t}-y_{g,t})
```
$`AcoPar_{g,t}:\ Coherencia\ arranque\ acoplamiento\ parada`$
```math
y_{g,t}-v_{g,t}-z_{g,t}+v_{g,t-1}+[EI_{g}]_{t=1}=0
```
$`RampSub_{g,t}:\ Limita\ la\ rampa\ de\ subida`$
```math
p_{g,t} - p_{g,t-1} - [PI_{g}]_{t=1} \leq RS_{g}
```
$`RampBaj_{g,t}:\ Limita\ la\ rampa\ de\ bajada`$
```math
p_{g,t-1} + [PI_{g}]_{t=1} - p_{g,t} \leq RB_{g}
```