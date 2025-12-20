# ================================
# Project: LaunchForge
# Description:
# A top-tier launchpad for transforming ideas into polished solutions.
# Built for momentum, innovation, and long-term growth.
# ================================

# ---------- main.py ----------
"""
Main entry point for LaunchForge.
"""

from core.pipeline import Idea-Pipeline
from core.growth import GrowthEngine


def run():
    print("🚀 LaunchForge Initialized")
    print("⚡ Momentum | 💡 Innovation | 📈 Long-Term Growth\n")

    pipeline = IdeaPipeline()
    growth = GrowthEngine()

    # Momentum: fast iteration
    raw_ideas = ["optimize", "scale", "secure"]
    refined = pipeline.refine(raw_ideas)
    print("⚙️ Refined Ideas:", refined)

    # Innovation: score and prioritize
    scored = pipeline.score(refined)
    print("💡 Innovation Scores:", scored)

    # Growth: long-term projection
    metrics = {"users": 100, "performance": 0.85}
    print("📈 Growth Projection:", growth.project(metrics, years=3))


if __name__ == "__main__":
    run()


# ---------- core/pipeline.py ----------
"""
Pipeline for turning raw ideas into structured, polished solutions.
"""

from typing import List, Dict

class IdeaPipeline:
    """Transforms ideas through refinement and evaluation stages."""

    def refine(self, ideas: List[str]) -> List[str]:
        """Clean and normalize idea inputs."""
        return [idea.strip().lower() for idea in ideas if idea]

    def score(self, ideas: List[str]) -> Dict[str, float]:
        """Assign innovation scores based on idea characteristics."""
        scores = {}
        for idea in ideas:
            scores[idea] = round(len(idea) * 0.7 + 1.5, 2)
        return scores


# ---------- core/growth.py ----------
"""
Growth and sustainability logic for long-term project evolution.
"""

class GrowthEngine:
    """Models long-term growth and system evolution."""

    def project(self, metrics: dict, years: int = 1) -> dict:
        """
        Project system growth over time.
        """
        projection = {}
        for key, value in metrics.items():
            projection[key] = round(value * (1 + 0.15 * years), 2)
        return projection

    def reinforce(self, metrics: dict) -> dict:
        """Strengthen core metrics for stability."""
        return {k: round(v * 1.05, 2) for k, v in metrics.items()}


# ---------- tests/test_pipeline.py ----------
"""
Tests for idea pipeline.
"""

from core.pipeline import IdeaPipeline

def test_refine():
    pipeline = IdeaPipeline()
    assert pipeline.refine([" Test ", ""]) == ["test"]

def test_score():
    pipeline = IdeaPipeline()
    scores = pipeline.score(["build"])
    assert scores["build"] > 0


# ---------- tests/test_growth.py ----------
"""
Tests for growth engine.
"""

from core.growth import GrowthEngine

def test_project():
    engine = GrowthEngine()
    result = engine.project({"users": 100}, years=2)
    assert result["users"] > 100

