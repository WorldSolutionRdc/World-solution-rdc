# Proxy Nginx pour VPS (45.61.52.208)

Proxy Nginx déployé sur Google Cloud Run pour rediriger le trafic TCP vers le VPS principal.

## Configuration
| Élément | Valeur |
|---------|--------|
| **VPS cible** | `45.61.52.208:443` |
| **Port d'écoute proxy** | `8080` |
| **Région VPS** | `us-west2` (Los Angeles, Californie, USA) |
| **Région Cloud Run** | `us-west2` (Los Angeles, Californie, USA) |
| **Type de proxy** | TCP Stream (Layer 4) |

## Déploiement
```bash
gcloud run deploy ultra-speed-proxy \
  --source . \
  --platform managed \
  --region us-west2 \
  --allow-unauthenticated \
  --port 8080 \
  --memory 512Mi \
  --cpu 1 \
  --timeout 3600
