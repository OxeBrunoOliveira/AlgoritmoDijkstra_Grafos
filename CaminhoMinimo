from IPython.utils.text import string
import heapq

def dijkstra(grafo, inicio, fim):
    distancias = {vertice: float('inf') for vertice in grafo}
    distancias[inicio] = 0
    fila = [(0, inicio)]
    while fila:
        (dist, atual) = heapq.heappop(fila)
        if atual == fim:
            return dist
        for vizinho in grafo[atual]:
            custo = grafo[atual][vizinho]
            distancia_atualizada = dist + custo
            if distancia_atualizada < distancias[vizinho]:
                distancias[vizinho] = distancia_atualizada
                heapq.heappush(fila, (distancia_atualizada, vizinho))
    return -1

grafo = {
    'CIDADE A': {'CIDADE B': 10, 'CIDADE C': 3},
    'CIDADE B': {'CIDADE C': 1, 'CIDADE D': 2},
    'CIDADE C': {'CIDADE B': 4, 'CIDADE D': 8, 'CIDADE E': 2},
    'CIDADE D': {'CIDADE E': 7},
    'CIDADE E': {'CIDADE D': 9, 'CIDADE A': 12, 'CIDADE C': 6}
}

ponto_inical = 'CIDADE A'
ponto_final = 'CIDADE D'
distancia = dijkstra(grafo, ponto_inical, ponto_final)
print(f'A distancia entre a {ponto_inical} até a {ponto_final} é igal a {distancia}.')
