
# Si ome si

{{< mermaid >}}
flowchart LR
  A["🌍 <b>Internet</b><br>Origen del tráfico<br>Usuarios externos, clientes, bots"]
  subgraph AWS
    B["🧭 <b>VPC</b><br>Aislamiento lógico<br>Control de rutas (Route Tables)<br>Define destinos alcanzables"]
    subgraph Subred
      C["🛡️ <b>NACL</b><br>Nivel de subred<br>Stateless<br>Permite o deniega tráfico<br>Reglas ordenadas por número"]
      subgraph EC2
        D["🔐 <b>Security Group</b><br>Nivel de instancia (ENI)<br>Stateful<br>Solo reglas Allow (Deny implícito)<br>Retorno automático<br>Puede referenciar otros SGs"]
        subgraph Sistema Operativo
          E["🧱 <b>Firewall del SO</b><br>(Windows Firewall / iptables)<br>Control por puerto, proceso o usuario"]
          F["⚙️ <b>Aplicación / Servicio</b><br>Autenticación, autorización y cifrado<br>Control de acceso interno"]
        end
      end
    end
  end

  A ---> B
  B ---> C
  C ---> D
  D ---> E
  E ---> F

  F -.-> E
  E -.-> D
  D -.-> C
  C -.-> B
  B -.-> A
{{< /mermaid >}}

guyk
